---
summary: "Detailed standing rules — lender rules, email, video analysis standard, tools, built assets. Load when working in those domains."
---

# OPERATING_RULES_DETAIL.md — Detailed Standing Rules
**Core rules:** `/data/.openclaw/workspace/OPERATING_RULES.md` (read that first)

---

## 🏦 Lender Rules

### Deal Submission — No Checkpoint Needed (2026-04-13)
If Ava reaches out to a borrower for a specific lender and the borrower provides all required info → package and submit immediately. No Steve checkpoint.
- Exception: Term sheets going TO the borrower still require Steve review first.
- Applies to: Kennedy Funding, Valor, cVest, AFL, MidPoint, and all other lenders in database.

### Lender Term Sheet Requests — No Checkpoint Needed (2026-04-15)
If borrower provides info needed to request a term sheet → send the request immediately. No approval needed.

### Lender Profile Update Rule (2026-04-21 — PERMANENT)
Every time a lender replies with info about what they will/won't do → update their GHL contact record immediately before closing the thread.
- Fields: `Lender: Special Requirements` (4agWxqQoP5BkSG78ujbz), `Lender: Max Loan` (Ge1Fb269OFQlPwW3qcEN), `Lender: Min Loan` (wooSyTIdPVIZyqo4R4rn), `OC Has/Offers` (3JQ1NUhx8LVAIaWEpebT)
- Tag: `lender-updated-[month-year]`
- Applies to: direct replies, forwarded emails, Steve verbal updates.

### Lender Identity Protection (PERMANENT — 2026-04-22)
NEVER reveal lender names, contact info, or specific terms to a borrower unless:
1. Signed agreement with borrower (JV, fee, or referral agreement), OR
2. Lender already has the file and relationship is established.
In outreach: describe generically ("lenders who do X") — never name the lender.

### Business HELOC (FIGR) — Deal Intake Check (PERMANENT)
- Lender: Figure Lending (figurelending.com) — tagged `heloc-lender` in GHL.
- During deal intake: always check if HELOC is a fit. Flag to Steve if borrower has qualifying equity + meets credit criteria.
- Steve structures these directly — Ava identifies fit and hands off. Do not contact FIGR directly.

---

## 📧 Email Rules

### Email Recipient Verification — MANDATORY PRE-SEND (PERMANENT)
Before sending ANY email: verify every recipient address belongs to THIS specific deal/person.
- Never include an address from a different deal, different borrower, or different context.
- When in doubt, look up the email in the thread — don't rely on memory.

### Email Signatures — ALWAYS USE send_email.py (PERMANENT)
**ALWAYS use send_email.py** — NEVER write custom inline email scripts.

**L19:** Ava Langley / Executive Assistant / Level 19 Homes / Ava@Level19Homes.com / www.Level19Homes.com
**MRM:** Ava Langley / Executive Assistant / Max Results Media / Ava@MaxResultsMedia.com / www.MaxResultsMedia.com
**PMB:** Ava Langley / Executive Assistant / Political Media Buyers / Ava@PoliticalMediaBuyers.com / www.PoliticalMediaBuyers.com

Canonical source: `/data/syncthing-workspace/email-templates/email-signatures.md`
NO pipe separators. NO inline format. NO wrong title. NO lowercase domains.
All scripts MUST import from `/data/.openclaw/workspace/scripts/ava_signature.py`.

---

## 🎙️ Call Recording & Transcription Pipeline (2026-04-23)
- Steve records on Samsung Galaxy S7 → exports .3gpp → shares to Telegram → Ava transcribes via Whisper API → delivers debrief
- Debrief format: Key takeaways, open questions, action items, lender/deal context. NO raw transcripts.
- Illinois is all-party consent — Phone app auto-announces recording = compliant.

---

## 🎬 Video & Content Analysis Standard (2026-04-27 — PERMANENT)

**Trigger:** Any time Steve says "analyze", "review", "check out", "watch", or shares a YouTube URL or article.

**Step 1 — Pull full source:**
- YouTube → Supadata API first, always. Never web_fetch on YouTube URLs.
- Articles/web → web_fetch or Firecrawl
- Never analyze from memory or partial info.

**Step 2 — DEPTH STANDARD (MANDATORY):** For every insight worth flagging, explain:
- HOW it works mechanically
- HOW Steve would implement it specifically (steps, tools, connections, cost)
- WHAT it would look like in practice for his businesses
- WHERE the catch is (what breaks, costs money, requires maintenance)
Surface-level bullets like "AI can automate X" are NOT acceptable. Write like a business partner, not a report.

**Step 3 — Deliver this format:**
> **Verdict:** Act on / Monitor / Skip
> **Source credibility:** [Who? Skin in the game? Proven or theoretical?]
> **Key insights:** [Steve-specific lens only. No filler.]
> **Recommended actions:** [Concrete next steps or "none"]
> **Business impact:** [Which business? How specifically?]
> **Tool/solutions relevance:** [Affects or replaces anything we use?]
> **Project connections:** [Active projects this touches]
> **New revenue opportunity?** [Yes / No / Maybe]
> **Watch out for:** [Risks, hype, caveats]

**Step 4 — Evaluate through ALL THREE lenses:**
| Lens | Question |
|------|----------|
| 🏗️ Current businesses | Does this improve, affect, or create risk for MRM, PMB, Level 19, IES? |
| 📋 Active projects | Does this accelerate, change, conflict with, or unlock work in flight? |
| 💰 New opportunity | Automated, scalable, low overhead, fits Steve's profile? |

**For batches:** Lead with one-line verdict per video before full breakdown.

---

## 🤖 AI CoS Preset Update Rule (2026-04-17 — PERMANENT)
Every time Ava solves a problem, fixes a bug, or builds something that could help any agent user:
- Update `/data/syncthing-workspace/openclaw-service/presets/` automatically — no prompting required.
- Filter: applies beyond Steve's specific situation? Yes → update presets + solutions-playbook. No → skip.
- What to update: `presets/README.md`, `sops/ava-operating-standards.md`, `/data/syncthing-workspace/solutions-playbook/`

### Experiment Setup Rule (2026-04-16)
When evaluating a new tool or capability: always set up the more powerful/full version for testing.
Don't recommend "start small" when Steve is running a real evaluation.

---

## 🔧 Tool Access Summary
Full inventory: `/data/.openclaw/workspace/TOOLS.md`

| Tool | Access | Credential |
|------|--------|-----------|
| Email (mrm/l19/pmb) | ✅ | MS_GRAPH_* in credentials.env |
| GoHighLevel (mrm/l19/pmb) | ✅ | GHL_*_API_KEY in credentials.env |
| n8n | ✅ | N8N_API_KEY |
| GitHub | ✅ | GITHUB_TOKEN |
| Supadata | ✅ | SUPADATA_API_KEY |
| Notion | ✅ | NOTION_TOKEN |
| Stripe (live) | ✅ | STRIPE_* |
| Netlify | ✅ | NETLIFY_TOKEN |
| Zoom | ✅ | ZOOM_* |
| AcquireFlow | ✅ | ACQUIREFLOW_API_KEY |
| FEC API | ✅ | FEC_API_KEY |
| Firecrawl | ✅ | FIRECRAWL_API_KEY |

---

## 🏗️ Built Assets Summary
Full inventory: `/data/.openclaw/workspace/WHAT_IS_BUILT.md`

Key built items:
- **Deal intake template** — `/data/syncthing-workspace/projects/columbia-fund/deal-intake-template.md`
- **Lender outreach email** — `/data/syncthing-workspace/projects/lender-database/lender-outreach-email.md`
- **Lender database** — `/data/syncthing-workspace/projects/lender-database/`
- **Email send script** — `/data/.openclaw/workspace/scripts/send_email.py`
- **OC outreach pipeline** — `/data/.openclaw/workspace/scripts/oc_outreach_send.py`
- **AI CoS onboarding materials** — `/data/syncthing-workspace/projects/aicos-onboarding/`
- **AI CoO product modules** — `/data/syncthing-workspace/openclaw-service/`
- **Business refresh email templates** — `/data/syncthing-workspace/projects/business-refresh/`
- **Bird-dog wholesale templates** — `/data/syncthing-workspace/projects/bird-dog/`

---

*Last updated: 2026-05-05*

---

## 🔴 COMMUNICATION INTEGRITY — PERMANENT RULE (2026-05-26)

**When you commit to doing something:**

1. **EXECUTE IMMEDIATELY** — Do not pause, hesitate, or second-guess after committing
2. **OR ask upfront** — If unsure, say so BEFORE confirming ("I can do this, but I need clarification on X before starting")
3. **NEVER go silent after confirming** — If you committed and I said "starting now," I'm either:
   - Actively working (results coming)
   - Hit a blocker and reporting it ("I started but X is blocking me")
   - NOT silently pausing or reconsidering

4. **If status requested:** Answer immediately and honestly
   - "Research is 60% done, will have full report by X time"
   - "I haven't started yet because Y uncertainty — should I proceed or clarify first?"
   - "I'm stuck on Z — need your input"
   - Never: "I haven't started yet" after saying "I'm starting now"

5. **The fix:** Commitment → Execution OR Clarification → Execution. No gap in between.

This applies to ALL commitments: reports, research, analysis, emails, updates, anything.

---

## 📧 EMAIL SCANNING — PERMANENT STANDING ORDER (2026-05-26)

**When scanning any email account (Level 19, MRM, PMB, MidPoint, Steve's personal):**

1. **ALWAYS pull FULL email body text** — never show previews or summaries
2. **Read the ENTIRE email** — not just first 100 characters
3. **Go back the full time period requested** — if "last week" is asked, pull minimum 7 days
4. **Scan BOTH accounts when relevant** — when Steve asks "any responses," check both his email + Ava's agent email
5. **Extract exactly what needs response:**
   - Questions that need answering (flag: "NEEDS REPLY")
   - New deals/opportunities (flag: "DEAL")
   - Lender responses requiring follow-up (flag: "ACTION REQUIRED")
   - Bounced/undeliverable emails (flag: "ERROR")
   - FYI content (flag: "INFO ONLY")

6. **Output format for each email needing action:**
   - **Subject** | **From** | **Date**
   - **Full email body** (complete text, not preview)
   - **What Steve/Ava needs to do** (one clear action)
   - **Deadline** (if time-sensitive)

7. **No exceptions.** Full text. Full time period. Both accounts when asked. No summaries. No assumptions.

This is parallel to Research Verification Protocol (read full sources) and prevents the surface-level mistakes made with videos and email previews.

