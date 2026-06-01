# Solution: Live Deal Dashboard from GHL (Netlify)
**Category:** Dashboard / CRM / Automation  
**Created:** 2026-04-17 by Ava  
**Pattern:** GHL pipeline → JS fetch → Netlify static site  
**Status:** ✅ Proven and live at l19-deal-dashboard.netlify.app

---

## What This Solves

You want a real-time deal dashboard that auto-updates without manual rebuilds. The solution: a static HTML page hosted on Netlify that fetches live from GoHighLevel's API every 5 minutes. No backend, no database, no server — just a URL that's always current.

---

## Architecture

```
GoHighLevel (source of truth)
    ↓  GHL API (client-side fetch from browser)
Netlify static HTML page
    ↓  Renders in real time
l19-deal-dashboard.netlify.app
```

**Key principle:** GHL is the database. The dashboard is just a reader. All updates go into GHL — the dashboard shows whatever GHL has.

---

## How It Works

1. HTML page loads in browser
2. JavaScript calls GHL Opportunities API directly (no proxy needed — GHL allows CORS from browser)
3. Data is parsed and rendered into a sortable table + Kanban board
4. Auto-refreshes every 5 minutes; manual refresh button also available
5. No server-side code, no cron, no token cost to Ava

---

## ⚡ API Cost Reality Check

**The 5-minute refresh does NOT cost Ava anything in tokens or API fees.** Here's why:

- The fetch happens **in the user's browser** — not on the VPS, not through OpenClaw
- GHL API calls are covered by the GHL subscription (no per-call charges on standard plan)
- Ava's Claude/OpenClaw tokens are only used when Ava actively processes something in a session
- Passive fetches (browser → GHL) have zero impact on Ava's context, model costs, or performance

**What DOES cost tokens:** Ava reading emails, writing responses, running analysis, cron jobs that trigger agent turns. The dashboard itself is free to run once built.

---

## Setting Up a Dashboard Like This

### Step 1 — GHL Pipeline Setup
- Create a Pipeline in GHL for the relevant object (deals, leads, etc.)
- Define stages that match your workflow (Intake → Gathering Info → Submitted → Term Sheet → Closed)
- Create custom fields for the data you want to display:
  - Text fields: Property Address, Lenders, Next Step, Waiting On, Loan Type
  - Number fields: Loan Amount, Fee %, Fee $
  - These fields will be referenced by ID in the dashboard code

### Step 2 — Get Your GHL IDs
You need 3 things before writing any dashboard code:
1. **Location ID** — from GHL settings or API response
2. **Pipeline ID** — from `GET /opportunities/pipelines?locationId=...`
3. **Custom Field IDs** — from any opportunity record's `customFields` array

```bash
# Get pipelines + stage IDs
curl -s "https://services.leadconnectorhq.com/opportunities/pipelines?locationId=YOUR_LOCATION_ID" \
  -H "Authorization: Bearer YOUR_API_KEY" -H "Version: 2021-07-28"

# Get custom field IDs from a real opportunity
curl -s "https://services.leadconnectorhq.com/opportunities/OPPORTUNITY_ID" \
  -H "Authorization: Bearer YOUR_API_KEY" -H "Version: 2021-07-28"
```

### Step 3 — Build the HTML Dashboard
The dashboard is a single HTML file with:
- GHL credentials hardcoded (API key + location/pipeline IDs) — acceptable for internal dashboards
- `loadData()` function that fetches from GHL and maps custom fields by ID
- `parseDeal()` that extracts loan amount, stage, lenders, waiting on, next step from custom field IDs
- Table view (sortable columns) + Kanban view (grouped by stage)
- Stats bar: Active Deals, Total Loan Volume, Pipeline Revenue, Waiting on Steve, Closed

Key CF mapping in code:
```js
const CF = {
  broker: 'YOUR_CF_ID',
  loan_amount: 'YOUR_CF_ID',
  fee_pct: 'YOUR_CF_ID',
  fee_dollars: 'YOUR_CF_ID',
  property: 'YOUR_CF_ID',
  lenders: 'YOUR_CF_ID',
  waiting_on: 'YOUR_CF_ID',
  next_step: 'YOUR_CF_ID',
  loan_type: 'YOUR_CF_ID'
};
```

### Step 4 — Deploy to Netlify
```bash
# Create a deploy folder with index.html
mkdir /tmp/dashboard-deploy
cp your-dashboard.html /tmp/dashboard-deploy/index.html

# Zip and deploy via Netlify API
cd /tmp/dashboard-deploy && zip -r deploy.zip index.html

curl -X POST "https://api.netlify.com/api/v1/sites/YOUR_SITE_ID/deploys" \
  -H "Authorization: Bearer YOUR_NETLIFY_TOKEN" \
  -H "Content-Type: application/zip" \
  --data-binary @deploy.zip
```

### Step 5 — Verify It Works
1. Open the URL in browser
2. Check browser console (F12) for API errors
3. If data shows but is stale: the issue is GHL custom fields not being updated — NOT the dashboard
4. If no data at all: check API key, location ID, pipeline ID

---

## ⚠️ Common Failure Mode #3 — GHL Returns fieldValueString/fieldValueNumber (Found Apr 22)

**Symptom:** Dashboard renders (no raw code), deal names and stages show, but ALL custom field columns are blank. Waiting On, Next Step, Property, Lenders all show `—`.

**Root cause:** GHL Opportunities API (v2021-07-28) returns custom fields with typed keys:
- String fields → `fieldValueString`
- Number fields → `fieldValueNumber`
- NOT `fieldValue` or `value`

This is different from what the `customFields` list endpoint returns and changes between API versions.

**Wrong:**
```js
function getCustomField(opp, fieldId) {
  const cf = (opp.customFields || []).find(f => f.id === fieldId);
  return cf ? cf.value : null;  // ❌ undefined
}
```

**Correct (handles all GHL field key variants):**
```js
function getCustomField(opp, fieldId) {
  const cf = (opp.customFields || []).find(f => f.id === fieldId);
  if (!cf) return null;
  if (cf.fieldValueString !== undefined) return cf.fieldValueString;
  if (cf.fieldValueNumber !== undefined) return cf.fieldValueNumber;
  return cf.fieldValue || cf.value || null;  // fallback for older API versions
}
```

**How to verify:** Run a raw API call on one opportunity and inspect the `customFields` array keys. If you see `fieldValueString` instead of `value`, use the fixed version above.

---

## ⚠️ Common Failure Mode #4 — Netlify Deploys as Plain Text (Found Apr 22)

**Symptom:** Dashboard URL shows raw HTML/CSS source code instead of rendering the page.

**Root cause:** Netlify zip deploy without a `_headers` file defaults to incorrect MIME type on some deploys.

**Fix:** Always include a `_headers` file in the deploy zip:
```
/*
  Content-Type: text/html; charset=utf-8
```

**Deploy pattern that works:**
```python
import zipfile
z = zipfile.ZipFile('/tmp/deploy.zip', 'w', zipfile.ZIP_DEFLATED)
z.write('index.html', 'index.html')
z.write('_headers', '_headers')  # Always include this
z.close()
```

---

## ⚠️ Common Failure Mode #2 — GHL API Field Key Bug (Found Apr 17)

**Symptom:** Dashboard loads, deal names and stages show, but all custom field columns (Property, Waiting On, Next Step, Lenders, Fee) are blank or show wrong values. Fee shows as same as Loan Amount.

**Root cause:** GHL Opportunities API returns custom fields with key `fieldValue`, not `value`. If your JS does `cf.value`, it silently gets `undefined` for every field.

**Wrong:**
```js
function getCustomField(opp, fieldId) {
  const cf = (opp.customFields || []).find(f => f.id === fieldId);
  return cf ? cf.value : null;  // ❌ GHL sends fieldValue, not value
}
```

**Correct:**
```js
function getCustomField(opp, fieldId) {
  const cf = (opp.customFields || []).find(f => f.id === fieldId);
  return cf ? (cf.fieldValue !== undefined ? cf.fieldValue : cf.value) : null;  // ✅
}
```

**Secondary symptom:** Fee column shows same number as Loan Amount. This happens because `getCustomField(opp, CF.loan_amount)` returns null, so the code falls back to `opp.monetaryValue` for the loan — and then the fee calculation uses that same fallback value before the CF fee field is read.

---

## ⚠️ Common Failure Mode #1 — Stale Data (What Went Wrong Apr 17)

**Symptom:** Dashboard refreshes but shows outdated info.  
**Root cause:** GHL deal records (custom fields) were not being updated as deals progressed. The dashboard faithfully showed whatever was in GHL — which was stale.  
**Fix:** Update GHL deal records every time a deal status changes. Stage, loan amount, lenders, next step, waiting on — all must be kept current in GHL.  
**Prevention:** Whenever Ava takes an action on a deal (submits to lender, receives term sheet, etc.), update the GHL opportunity in the same action sequence.

---

## Ongoing Maintenance Rule

**Every time a deal status changes → update GHL immediately:**
```bash
curl -X PUT "https://services.leadconnectorhq.com/opportunities/OPP_ID" \
  -H "Authorization: Bearer $GHL_L19_API_KEY" \
  -H "Version: 2021-07-28" \
  -H "Content-Type: application/json" \
  -d '{"pipelineStageId": "STAGE_ID", "monetaryValue": AMOUNT, "customFields": [...]}'
```

The dashboard takes care of itself. GHL is the only thing that needs maintenance.

---

## Level 19 Specific Details

- **Site ID:** `fb07ee7f-7484-46b6-ac77-600c40a3af91`
- **Site URL:** https://l19-deal-dashboard.netlify.app
- **GHL Location:** L19 GHL (`GHL_L19_LOCATION_ID` in credentials.env)
- **Pipeline ID:** `OcAxniuyqpUcxAULZTcX` (Level 19 Deal Pipeline)
- **API Key:** `GHL_L19_API_KEY` in credentials.env
- **Netlify Token:** `NETLIFY_TOKEN` in credentials.env
- **Source file (canonical):** `/data/.openclaw/workspace/deal-dashboard/index.html`
- **Field mapping doc:** `/data/syncthing-workspace/projects/deal-pipeline/GHL-OPPORTUNITY-FIELDS.md`

### Current Custom Field IDs (L19 Opportunity fields)
| Field | ID |
|---|---|
| Waiting On | `CMas0XwS78xg1MNZ9PcY` |
| Next Step | `MvKABSIyHZWrDePzscwU` |
| Loan Amount | `DQOXijOwqL8aNioPRlMy` |
| Fee % | `XiFytHoznPZ8DOYVk7ru` |
| Fee $ | `lDB9zfcvS9LSSJTCaEpx` |
| Loan Type | `SpGS1YeNAmfU2SspHEcD` |
| Property | `D0HwqnVGrXI6DIOe5RLu` |
| Lenders | `JvVJ4TijlP1cI1ZsVZGP` |
| Broker | `45sshtSROTVStg0DKGRO` |

### Dashboard Layout (as of Apr 22, 2026)
- **Columns:** Deal/Borrower | Property | Stage | Loan/Fee | Waiting On + Next Step (combined) | Days in Stage | Lender(s)
- **Waiting On** field stores a short description (e.g. "Lender — MidPoint reviewing credit explanation")
- **Next Step** field stores the full action description
- Both render together in the Waiting On column — badge on top, detail text below
- Dead/Lost and Closed/Won hidden by default (checkboxes to show)

### How to Update a Deal
```bash
bash -c 'source /data/.openclaw/workspace/credentials.env && curl -s -X PUT \
  "https://services.leadconnectorhq.com/opportunities/OPP_ID" \
  -H "Authorization: Bearer \$GHL_L19_API_KEY" \
  -H "Version: 2021-07-28" \
  -H "Content-Type: application/json" \
  -d "{\"customFields\": [{\"id\": \"CMas0XwS78xg1MNZ9PcY\", \"value\": \"Waiting On text\"}, {\"id\": \"MvKABSIyHZWrDePzscwU\", \"value\": \"Next Step text\"}]}"'
```

### How to Redeploy Dashboard
```python
import zipfile
# 1. Edit /data/.openclaw/workspace/deal-dashboard/index.html
# 2. Create _headers file with: /*\n  Content-Type: text/html; charset=utf-8
# 3. Zip both files
z = zipfile.ZipFile('/tmp/deploy.zip', 'w', zipfile.ZIP_DEFLATED)
z.write('/tmp/deploy/index.html', 'index.html')
z.write('/tmp/deploy/_headers', '_headers')
z.close()
# 4. POST zip to Netlify API (site fb07ee7f-7484-46b6-ac77-600c40a3af91)
```

---

*Written by Ava — 2026-04-17. Updated 2026-04-22 with fieldValueString fix, Netlify content-type fix, current field IDs, and layout changes.*
