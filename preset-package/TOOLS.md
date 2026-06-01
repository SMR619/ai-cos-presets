---
summary: "Ava's full tool inventory — deep reference. For quick credential lookups, use CREDENTIALS.md instead."
---

# TOOLS.md — Ava's Full Tool Inventory
**Quick credential lookups:** Use `CREDENTIALS.md` — it's faster and lighter.
**This file:** Full tool descriptions, context, notes, and research. Read when you need the full picture on a tool.
**Credentials are in:** `/data/.openclaw/workspace/credentials.env`

---

## Microsoft Graph — Max Results Media (mrm)
- **Access:** API (client credentials flow)
- **Credentials:** `MS_GRAPH_CLIENT_ID`, `MS_GRAPH_TENANT_ID`, `MS_GRAPH_CLIENT_SECRET`, `MS_GRAPH_OBJECT_ID`
- **Email address:** ava@maxresultsmedia.com
- **Use for:** Sending/reading email for MRM account, media/general/outreach
- **Script:** `/data/.openclaw/workspace/scripts/send_email.py --account mrm`
- **Notes:** Always HTML. Never Himalaya. Signature auto-appended.

## Microsoft Graph — Level 19 Homes (l19)
- **Access:** API (client credentials flow)
- **Credentials:** `MS_GRAPH_L19_CLIENT_ID`, `MS_GRAPH_L19_TENANT_ID`, `MS_GRAPH_L19_CLIENT_SECRET`
- **Email address:** ava@level19homes.com
- **Use for:** Sending/reading email for real estate, deals, lending, lender outreach
- **Script:** `/data/.openclaw/workspace/scripts/send_email.py --account l19`
- **Notes:** Always HTML. Use for all Level 19 / deal-related email.

## Microsoft Graph — MidPoint Capital Partners (midpoint)
- **Access:** API (client credentials flow)
- **Credentials:** `MIDPOINT_MS_TENANT_ID`, `MIDPOINT_MS_CLIENT_ID`, `MIDPOINT_MS_CLIENT_SECRET`
- **Email addresses:**
  - `steveross@midpointecapitalpartners.com` (Steve's MidPoint inbox)
  - `avalangley@midpointecapitalpartners.com` (Ava's MidPoint inbox)
  - Full read access to all MidPoint email accounts via Graph API
- **Use for:** MidPoint Capital deal communications, reading/sending on behalf of Steve or Ava at MidPoint
- **Script:** Use `send_email.py` pattern with midpoint credentials, or direct Graph API calls
- **Notes:** Always HTML. Tenant ID: `8f3ae1a0-80b8-4a83-988f-f66b90cd497b`

## Microsoft Graph — Political Media Buyers (pmb)
- **Access:** API (client credentials flow)
- **Credentials:** `MS_GRAPH_PMB_CLIENT_ID`, `MS_GRAPH_PMB_TENANT_ID`, `MS_GRAPH_PMB_CLIENT_SECRET`, `MS_GRAPH_PMB_OBJECT_ID`
- **Email address:** ava@politicalmediabuyers.com
- **Use for:** All PMB / political campaign email
- **Script:** `/data/.openclaw/workspace/scripts/send_email.py --account pmb`
- **Notes:** Always HTML.

---

## GoHighLevel — Max Results Media (AI CoS product)
- **Access:** API
- **Credentials:** `GHL_MRM_API_KEY`, `GHL_MRM_LOCATION_ID`
- **Use for:** AI CoS leads, MRM CRM contacts, dispatch emails for AI CoS signups
- **Notes:** 9 signups currently in system. Dispatch still blocked — mg.level19homes.com domain verification pending.

## GoHighLevel — Level 19 Homes
- **Access:** API
- **Credentials:** `GHL_L19_API_KEY`, `GHL_L19_LOCATION_ID`
- **Use for:** Level 19 real estate leads, AI CoS interested list
- **Notes:** Active. Use for real estate pipeline contacts.

## GoHighLevel — Political Media Buyers
- **Access:** API
- **Credentials:** `GHL_PMB_API_KEY`, `GHL_PMB_LOCATION_ID`
- **Use for:** PMB campaign contacts, 134 leads loaded
- **Notes:** Active. 134 leads already imported.

---

## n8n Cloud
- **Access:** API + web dashboard
- **Credentials:** `N8N_API_KEY`, `N8N_BASE_URL` (https://maxresultsmedia.app.n8n.cloud/api/v1)
- **Use for:** Workflow automation, webhook triggers, OC outreach pipeline, multi-step automations
- **Notes:** Pro plan ($60/mo, 10k executions). API key exists — do NOT ask Steve for it.

---

## GitHub
- **Access:** Personal access token
- **Credentials:** `GITHUB_TOKEN`, `GITHUB_USERNAME` (SMR619)
- **Use for:** Code repos, pushing/pulling files, repo management for Steve's projects
- **Notes:** Token exists — do NOT ask Steve for it.

---

## Supadata API
- **Access:** API
- **Credentials:** `SUPADATA_API_KEY`
- **Endpoint:** `https://api.supadata.ai/v1/youtube/transcript?url=<URL>&text=true`
- **Header:** `x-api-key: <key>`
- **Use for:** YouTube transcript extraction — ALWAYS try this first
- **Notes:** VPS IP is blocked by YouTube directly. This is the ONLY way to get transcripts.

---

## Notion
- **Access:** API
- **Credentials:** `NOTION_TOKEN`
- **Use for:** Notion database reads/writes, syncing with Ivy's workspace
- **Notes:** Token exists. Used for Ava ↔ Ivy cross-agent communication protocol.

---

## Stripe (MRM Live)
- **Access:** API (live keys)
- **Credentials:** `STRIPE_PUBLISHABLE_KEY`, `STRIPE_SECRET_KEY`
- **Use for:** Payment processing for MRM/AI CoS product
- **Notes:** Live keys (not test). Use carefully. Financial actions need Steve approval.

---

## Netlify
- **Access:** API + Pro plan dashboard
- **Credentials:** `NETLIFY_TOKEN`, `NETLIFY_AICOO_SITE_ID`
- **Use for:** Deploying/managing AI CoO landing page and web assets
- **Notes:** Pro plan ($20/mo). Site ID for AI CoO: `43612d03-82f3-43c4-9b76-d96d854a94cd`

---

## Zoom (Server-to-Server OAuth)
- **Access:** Server-to-Server OAuth
- **Credentials:** `ZOOM_ACCOUNT_ID`, `ZOOM_CLIENT_ID`, `ZOOM_CLIENT_SECRET`
- **Use for:** Zoom meeting management, call recording access, onboarding calls
- **Notes:** Server-to-server — no user login needed.

---

## AcquireFlow API
- **Access:** API
- **Credentials:** `ACQUIREFLOW_API_KEY`
- **Use for:** Level 19 real estate data, property acquisition pipeline
- **Notes:** API coming for Level 19 integration. Key already provisioned.

---

## FEC API (api.data.gov)
- **Access:** API
- **Credentials:** `FEC_API_KEY`
- **Use for:** Federal Election Commission data — campaign finance, donor lookup for PMB
- **Notes:** Free API from data.gov.

---

## OpenAI
- **Access:** Via OpenClaw configured model routing
- **Use for:** TTS (gpt-4o-mini-tts, Nova voice, 1.4x speed), image generation, model calls
- **Notes:** No direct API key needed — routed through OpenClaw.

---

## Ollie VPS
- **Access:** SSH / direct
- **Credentials:** `OLLIE_VPS_IP` (76.13.103.18), `OLLIE_VPS_ROOT_PASS`
- **Use for:** Secondary VPS, overflow compute
- **Notes:** Root access available. Use sparingly.

---

## Firecrawl
- **Access:** API
- **Credentials:** `FIRECRAWL_API_KEY`
- **Use for:** Web scraping, crawling, and content extraction from URLs
- **Notes:** Key provisioned April 13, 2026.

---

## Hostinger
- **Access:** Referral link
- **Credentials:** `HOSTINGER_REFERRAL_URL`
- **Use for:** Recommending hosting to clients/contacts
- **Notes:** Referral link only — not an API.

---

## OpenClaw (Primary Runtime)
- **Access:** CLI + cron + native tools
- **Cron jobs:**
  - Gateway watchdog: `db2eba3a` (every 5 min)
  - Syncthing watchdog: `6baccd79` (every 5 min)
  - OC Outreach: `7a6fe983` (Mon-Fri 8am-6pm CT, 15-20 emails/hr)
- **Use for:** All agent automation, cron scheduling, memory, tool routing
- **Notes:** In Docker containers: `openclaw gateway` (foreground), NOT `openclaw gateway start`.

---

## Pre-Solution Check — MANDATORY
Before proposing any tool, service, integration, or workflow solution:
1. Check TOOLS.md first — if we already have something that does the job, use it
2. Never recommend a third-party tool when an existing credential/API covers it
3. This applies to: email, CRM, automation, storage, data, payments, hosting — everything

*Last updated: 2026-05-18*
