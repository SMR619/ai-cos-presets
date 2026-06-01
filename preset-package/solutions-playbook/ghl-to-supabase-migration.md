# GHL → Supabase Migration: Proven Process
**Written:** 2026-05-27 | **Author:** Ava (learned from first implementation)
**Use when:** Moving contact/lender data from GoHighLevel into a Supabase relational database

---

## The Hard-Learned Rules

### 1. Never Use Python `urllib` for GHL Individual Contact Fetches
GHL's individual contact endpoint (`GET /contacts/{id}`) is protected by Cloudflare. Python's `urllib` gets 403'd. **Always use `subprocess` + `curl`.**

```python
import subprocess, json
result = subprocess.run(
    ['curl', '-s', f'https://services.leadconnectorhq.com/contacts/{contact_id}',
     '-H', f'Authorization: Bearer {api_key}',
     '-H', 'Version: 2021-07-28'],
    capture_output=True, text=True
)
contact = json.loads(result.stdout).get('contact', {})
```

### 2. GHL Search Endpoint Returns Truncated Custom Field IDs
The POST `/contacts/search` endpoint **truncates custom field IDs**. The individual GET endpoint returns the full IDs. Always fetch individual contacts to get full custom field data — don't rely on search results for field mapping.

### 3. Custom Field Prefix Matching
GHL custom field IDs are long UUIDs (e.g., `3JQ1NUhx8LVAIaWEpebT`). When mapping fields, **use startswith() prefix matching** against the known short prefix (e.g., `3JQ1NUhx8LVA`). This survives API version changes.

Known field prefixes for the Level 19 lender database:
| Prefix | Contains |
|--------|---------|
| `elfkLfGeYF1E` | Loan types |
| `3JQ1NUhx8LVA` | Notes/summary |
| `4agWxqQoP5Bk` | Criteria/requirements |
| `SDn2krpBCX3q` | States active |
| `X2IXqJVFqWUt` | Max LTV |
| `Ge1Fb269OFQl` | Max loan amount |
| `wooSyTIdPVIZ` | Min loan amount |
| `Pg7Necv5ZMt8` | Property types |
| `6TnC4hgjzhyU` | Broker notes |

### 4. Supabase Requires Service Role Key for Writes
The `SUPABASE_ANON_KEY` is blocked by Row Level Security (RLS) for inserts/updates.
**Always use `SUPABASE_SERVICE_ROLE_KEY`** when writing to Supabase from Ava.

```bash
curl -s -X POST "$SUPABASE_URL/rest/v1/lenders" \
  -H "apikey: $SUPABASE_SERVICE_ROLE_KEY" \
  -H "Authorization: Bearer $SUPABASE_SERVICE_ROLE_KEY" \
  -H "Content-Type: application/json" \
  -H "Prefer: return=representation" \
  -d '[{...}]'
```

### 5. `resolution=merge-duplicates` Doesn't Work Alone — Use PATCH for Updates
Supabase's `Prefer: resolution=merge-duplicates` doesn't reliably handle upserts on unique constraints. The reliable pattern is:
- **First insert:** `POST` with `Prefer: resolution=merge-duplicates`
- **Update existing:** `PATCH` with filter: `?ghl_contact_id=eq.{id}`

```bash
curl -s -X PATCH "$SUPABASE_URL/rest/v1/lenders?ghl_contact_id=eq.{cid}" \
  -H "apikey: $SUPABASE_SERVICE_ROLE_KEY" \
  -H "Authorization: Bearer $SUPABASE_SERVICE_ROLE_KEY" \
  -H "Content-Type: application/json" \
  -H "Prefer: return=representation" \
  -d '{...}'
```

### 6. Map to the ACTUAL Schema Columns
Always read the schema SQL file before inserting. Column names matter exactly.
For the lenders table: use `company` (not `name`), `ghl_contact_id` (not `ghl_id`).
Loan criteria (loan types, states, LTV, min/max) go in the **`loan_programs` table**, not `lenders`.

### 7. Relational Insert Pattern (lenders → loan_programs)
```python
# Step 1: Upsert lender, get back the UUID
resp = supabase_post("lenders", [lender_record])
lender_id = json.loads(resp)[0]['id']

# Step 2: Delete old programs, insert fresh
supabase_delete(f"loan_programs?lender_id=eq.{lender_id}")
supabase_post("loan_programs", [
    {"lender_id": lender_id, "loan_type": "bridge", "states": ["nationwide"], ...},
    {"lender_id": lender_id, "loan_type": "dscr", ...},
])
```

### 8. GHL Pagination
GHL uses cursor-based pagination. The `page=N` parameter doesn't work reliably past page 1.
Use `startAfter` + `startAfterId` from the `meta` object of each response.
Build the next URL manually — don't follow `nextPageUrl` directly (Cloudflare blocks it).

```python
params = f"locationId={location_id}&limit=100"
if start_after:
    params += f"&startAfter={start_after}&startAfterId={start_after_id}"
```

---

## Full Migration Workflow (Step by Step)

1. **Read the schema SQL** — confirm column names before writing a single line of code
2. **Get contact IDs** via GHL search POST (works fine for IDs + basic info)
3. **Fetch each contact** individually via curl subprocess to get full custom fields
4. **Map custom fields** using prefix matching
5. **Check if lender exists** in Supabase: `GET /rest/v1/lenders?ghl_contact_id=eq.{id}`
6. **If new:** POST to lenders table with correct column names
7. **If existing:** PATCH to lenders table using ghl_contact_id filter
8. **After lender upsert:** delete old loan_programs for that lender_id, insert fresh rows
9. **Use service role key** for all writes
10. **Log everything** — partial migration is better than nothing; don't stop on errors

---

## Common Errors and Fixes

| Error | Cause | Fix |
|-------|-------|-----|
| `403 Forbidden` from GHL | Cloudflare blocking Python urllib | Use subprocess + curl |
| `PGRST204 column not found` | Wrong column name | Read schema SQL first |
| `42501 RLS violation` | Using anon key for writes | Use SUPABASE_SERVICE_ROLE_KEY |
| `23505 duplicate key` | Record exists, merge-duplicates failed | Use PATCH instead of POST for updates |
| Truncated custom field IDs | Using search endpoint data | Fetch individual contact for full IDs |
| Double signatures in emails | Script auto-appended AND body contained sig | Script now auto-detects; or use `--no-signature` flag |

---

## Credentials Reference
All in `/data/.openclaw/workspace/credentials.env`:
- `GHL_L19_API_KEY` — Level 19 GHL API key
- `GHL_L19_LOCATION_ID` — Level 19 location ID
- `SUPABASE_URL` — Supabase project URL
- `SUPABASE_ANON_KEY` — Read-only (use for queries only)
- `SUPABASE_SERVICE_ROLE_KEY` — Full access (use for all writes)
