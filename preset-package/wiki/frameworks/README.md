# Frameworks Database — Syncthing Archive

**Purpose:** Human-readable backup of all frameworks. This directory auto-syncs from Supabase in real-time.

**Source of Truth:** Supabase `frameworks` table (queryable)  
**Always-Current Backup:** This directory (human-readable)  
**Sync Mechanism:** Real-time (happens when I add/update framework in Supabase)

---

## Files in This Directory

- **communication-frameworks.md** — All communication category frameworks (cold outreach, negotiation, objection handling, etc.)
- **business-frameworks.md** — All business category (strategy, offers, leads, revenue)
- **operations-frameworks.md** — All operations category (EOS, Traction, process design)
- **build-technical-frameworks.md** — All technical (app development, code patterns, architecture)
- **financial-frameworks.md** — All financial (pricing, margins, deal structure, money models)
- **INDEX.md** — Master searchable index (auto-generated)

---

## How to Use (If You're Browsing)

1. **Search by problem:** Use `INDEX.md` to find relevant framework
2. **Read summary:** Find the `.md` file for that category
3. **Need full details?** Read the linked file_path (original source SOP, playbook section, etc.)
4. **Want to add/edit?** Change in Supabase; Syncthing auto-updates

---

## Last Synced

This directory is kept current automatically. If you see stale content here, that means Supabase has been updated but sync hasn't happened yet (max 1 minute lag).

---

## Disaster Recovery

If Supabase becomes unavailable:
1. Read all frameworks from this directory
2. I re-import them to Supabase when available
3. No frameworks are lost; this is the durable copy
