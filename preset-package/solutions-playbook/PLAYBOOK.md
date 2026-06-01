# Solutions Playbook
**Last Updated:** 2026-04-02
**Maintained by:** Ava | **Reviewed by:** Steve Ross

> Before recommending any tool for a new project, check this document first. If the problem is already solved here, use the existing solution. Only evaluate alternatives if there's a specific reason it doesn't fit.

---

## 📋 TABLE OF CONTENTS

### Tools
1. [E-Signatures / Contract Signing](#1-e-signatures--contract-signing)
2. [Website Hosting](#2-website-hosting)
3. [CRM / Pipeline Management](#3-crm--pipeline-management)
4. [Email Sending (Agent / Transactional)](#4-email-sending-agent--transactional)
5. [Cold Email Outreach at Scale](#5-cold-email-outreach-at-scale)
6. [Website Analytics / A/B Testing](#6-website-analytics--ab-testing)
7. [File Sync — Agent to Human](#7-file-sync--agent-to-human)
8. [AI Model / Brain](#8-ai-model--brain)
9. [Invoicing / Accounting](#9-invoicing--accounting)
10. [Automation / Workflow Builder](#10-automation--workflow-builder)
11. [YouTube Transcription](#11-youtube-transcription)
12. [Payment Processing](#12-payment-processing)
13. [Document Storage / Shared Workspace](#13-document-storage--shared-workspace)
14. [MLS Property Offers](#14-mls-property-offers)
15. [Political Campaign Data](#15-political-campaign-data)
16. [SMS / AI Voice (After Hours)](#16-sms--ai-voice-after-hours)
17. [Website Builder for Client Sites](#17-website-builder-for-client-sites)
18. [TTS / Agent Voice](#18-tts--agent-voice)
19. [Code Versioning](#19-code-versioning)
20. [Deal Evaluation / Property Comps](#20-deal-evaluation--property-comps)

### Processes
21. [A/B Testing Landing Pages](#21-ab-testing-landing-pages)
22. [Email Harvesting / CRM Building from Inbox](#22-email-harvesting--crm-building-from-inbox)
23. [Bird Dog Deal Distribution](#23-bird-dog-deal-distribution)
24. [Build-in-Public Content System](#24-build-in-public-content-system)
25. [Agent Preset Distribution](#25-agent-preset-distribution)
26. [Commercial Loan Deal Intake & Submission](#26-commercial-loan-deal-intake--submission)
27. [Build-in-Public Content System (Full Stack)](#27-build-in-public-content-system-full-stack)
28. [AI Agent + CRM + Email Sync (The "Always-Updated Loop")](#28-ai-agent--crm--email-sync-the-always-updated-loop)

---

## TOOLS

---

### 1. E-Signatures / Contract Signing
**Problem:** Business owners need legally binding signatures on contracts, loan docs, JV agreements, and client agreements — without printing, scanning, or chasing people down.
**Solution:** Dropbox Sign (formerly HelloSign)
**Cost:** ~$15-25/mo (Steve already subscribing); full API access included
**Setup complexity:** Low
**Status:** Live ✅
**Why this over alternatives:** Steve has used it for years, it works, the API is clean and well-documented, and it's significantly cheaper than DocuSign for equivalent functionality. No reason to switch.
**Alternatives considered:**
- DocuSign — 3-5x more expensive, no meaningful capability advantage for our use case
- Adobe Sign — expensive, complex, enterprise-focused
- PandaDoc — better for proposals/templates, overkill for simple signing
**Ava integration:** Full API access. Ava can create signature requests, send to recipients, track status, and receive webhooks when signed. Already planned for loan doc automation.
**Notes:** Developer API credentials needed (Steve to pull from Account Settings → Integrations). Keep using — do not switch.

---

### 2. Website Hosting
**Problem:** Hosting multiple websites — client preview sites, landing pages, product pages — without paying per-site fees or managing servers.
**Solution:** Netlify Pro
**Cost:** $19/mo flat — unlimited sites, custom domains, serverless functions
**Setup complexity:** Low
**Status:** Live ✅
**Why this over alternatives:** One flat fee for unlimited sites is the only model that makes sense for Business Refresh (preview site per prospect). Deploy via CLI or drag-and-drop. Built-in split testing (A/B). Serverless functions for form capture. No per-site cost ever.
**Alternatives considered:**
- Vercel — comparable, but Netlify has better split testing built in and we're already set up
- GitHub Pages — free but no serverless functions, no split testing
- Cloudflare Pages — good but more complex setup
- Shared hosting (GoDaddy, Bluehost) — per-site cost, slow, not automatable
**Ava integration:** Full CLI + API. Ava deploys sites, creates redirects, runs split tests, manages domains programmatically. Token in credentials.env.
**Notes:** NETLIFY_TOKEN and NETLIFY_AICOO_SITE_ID in credentials.env. Site: aicoo-by-ava.netlify.app.

---

### 3. CRM / Pipeline Management
**Problem:** Managing contacts, deals, pipelines, email sequences, SMS, and automations across multiple businesses — without paying for 4 separate CRMs.
**Solution:** GoHighLevel (GHL)
**Cost:** ~$97-297/mo depending on plan; Agency Pro ($497/mo) needed for Business Refresh sub-account API
**Setup complexity:** Medium-High
**Status:** Live ✅ (MRM, L19, PMB accounts active)
**Why this over alternatives:** GHL does CRM + email + SMS + pipelines + automations + landing pages + reputation management in one platform. For our multi-business setup it's the only tool that handles all of it without stitching 5 tools together.
**Alternatives considered:**
- HubSpot — expensive at scale, not built for real estate/creative finance workflows
- Salesforce — enterprise overkill, expensive
- Zoho CRM — cheaper but weaker automation, less community support
- Airtable — not a CRM, more of a database; can supplement but doesn't replace
**Ava integration:** Full API for all three accounts. Ava creates/updates contacts, adds tags, logs notes, pushes to pipelines, reads contact data for deal matching. Keys in credentials.env (GHL_MRM, GHL_L19, GHL_PMB).
**Notes:** Agency Pro upgrade needed before Business Refresh sub-account automation goes live. GHL_MRM_API_KEY, GHL_L19_API_KEY, GHL_PMB_API_KEY + location IDs all in credentials.env.

---

### 4. Email Sending (Agent / Transactional)
**Problem:** The agent needs to send emails on Steve's behalf from real business email addresses — not a generic Gmail or no-reply address.
**Solution:** Microsoft Graph API (M365 accounts)
**Cost:** ~$6-12/user/mo (already paying for M365 accounts); Graph API is free
**Setup complexity:** Medium (OAuth app registration required)
**Status:** Live ✅
**Why this over alternatives:** M365 accounts are already set up for all three businesses. Graph API is rock solid, no third-party dependency, emails come from real business addresses (ava@maxresultsmedia.com, ava@level19homes.com, ava@politicalmediabuyers.com). Saves to Sent Items. Handles attachments.
**Alternatives considered:**
- Himalaya + Gmail — Google killed third-party app access in 2022. App passwords work but are fragile.
- SendGrid / Mailgun — good for bulk/transactional but not for personal-feeling outreach from a named agent
- SMTP relay — works but requires credentials that can expire or change
**Ava integration:** Full. Three Graph app registrations (MRM, L19, PMB). Object IDs, client IDs, tenant IDs, secrets all in credentials.env. Send script at `/data/.openclaw/workspace/scripts/send_email.py`.
**Notes:** MRM object ID: 5fc6a04c. L19 object ID: e5fdc067. PMB object ID pending. Never use Himalaya + Gmail — broken.

---

### 5. Cold Email Outreach at Scale
**Problem:** Sending hundreds of cold emails per day for Business Refresh prospect outreach without getting the root MRM domain flagged as spam.
**Solution:** Instantly.ai
**Cost:** ~$37/mo (Growth plan)
**Setup complexity:** Medium
**Status:** Planned 🔄
**Why this over alternatives:** Instantly handles warmup, sequencing, tracking, and inbox rotation. Protects the root domain by routing through a subdomain. Built specifically for cold outreach at volume.
**Alternatives considered:**
- Lemlist — comparable but more expensive (~$59/mo), more complex
- Mailshake — $59/mo, less automation
- Sending raw from MRM Graph — fine for 20-30/day (OC outreach), not for 200+/day at scale
- Apollo.io — great for prospecting but their email tool is secondary
**Ava integration:** API available for sequence management and reporting. Ava can create/manage campaigns via API when set up.
**Notes:** Set up Phase 2 of Business Refresh outreach. Use subdomain (e.g. outreach@[brand].maxresultsmedia.com) — do not route through root MRM domain for cold campaigns.

---

### 6. Website Analytics / A/B Testing
**Problem:** Tracking how many people visit landing pages, which version converts better, and whether content efforts are working — without cookie banners or sharing data with Google.
**Solution:** Plausible Analytics + Netlify split testing
**Cost:** Plausible: free tier / $9/mo (up to 10K pageviews); Netlify split testing: included in Pro plan (already paying)
**Setup complexity:** Low
**Status:** Setting up today 🔄
**Why this over alternatives:** Plausible is privacy-first (no cookies, GDPR compliant by default, no consent banner needed). Netlify handles the 50/50 traffic split natively. Together they give clean A/B data with variant tagging.
**Alternatives considered:**
- Google Analytics — privacy concerns, cookie banners required, overkill
- Hotjar — good for heatmaps but $39/mo and not needed yet
- Mixpanel — event tracking overkill for landing pages
**Ava integration:** Plausible Stats API returns JSON. Ava can pull variant performance data and report to Steve or write to Notion. Tracking script + variant props already embedded in follow.html (A) and follow-b.html (B).
**Notes:** Plausible account needs to be created by Steve (requires email verification). Once API key is provided, Ava configures site + Notion embed. A/B test: /follow (Version A) vs /follow-b (Version B). Netlify split rule to be configured after Plausible is live.

---

### 6b. Funnel Behavior Tracking & CRO — Microsoft Clarity
**Problem:** Knowing *why* a funnel isn't converting — not just the conversion rate, but where people drop off, what confuses them, what they click that doesn't work.
**Solution:** Microsoft Clarity (free heat maps + session recordings) + Claude MCP connector for plain-English analysis
**Cost:** Free
**Setup complexity:** Low (5-min GTM tag drop or paste into GHL/Netlify header)
**Status:** Active ✅ — SOP written 2026-04-15
**Rule:** Install on EVERY page/funnel/website we build or manage — no exceptions.
**Active installs needed:** AI CoS landing page, MyBuyBox (mybuybox.info), AI CoS questionnaire, Small Business Refresh client sites
**Why this over alternatives:**
- Hotjar: paid ($39+/mo). Clarity is identical features, free.
- GA4: traffic data only, no behavior/recordings
- GHL analytics: conversion rate only, no "why"
**Ava integration:** Once Claude MCP connector is added, Ava can query Clarity data directly. Weekly CRO review: pull top drop-off, run one split test, repeat.
**Key questions to ask Claude with Clarity connected:**
- "Where are people dropping off on my opt-in page?"
- "Compare paid ad visitors vs YouTube visitors on [page]"
- "What are the top dead clicks?"
- "Which step of the questionnaire has the highest exit rate?"
**Client use case:** Install on Small Business Refresh client sites as standard — gives us behavioral data to justify design decisions and differentiate from agencies that only look at traffic.
**Full SOP:** `/data/syncthing-workspace/sops/sop-microsoft-clarity-cro.md`

---

### 7. File Sync — Agent to Human
**Problem:** Files the agent creates (research, docs, templates, plans) need to be accessible on Steve's PC without manual downloads or cloud service logins.
**Solution:** Syncthing
**Cost:** Free (open source, self-hosted)
**Setup complexity:** Medium (one-time setup)
**Status:** Live ✅
**Why this over alternatives:** No cloud middleman. Files sync directly between VPS and Steve's PC. No Google Drive (blocked), no Dropbox (unnecessary cost), no data leaving controlled infrastructure. Works even if internet is spotty.
**Alternatives considered:**
- Google Drive — Steve's Gmail was suspended trying to set this up. Blocked.
- Dropbox — costs money, introduces a third party, no reason to use when Syncthing is free
- OneDrive — M365 included, being set up for Christina separately
**Ava integration:** Ava writes files to /data/syncthing-workspace/ — they appear on Steve's PC automatically. Watchdog cron (job ID: 6baccd79) runs every 5 min to keep the service alive.
**Notes:** Shared workspace: /data/syncthing-workspace/. Internal workspace: /data/.openclaw/workspace/. Syncthing watchdog cron active.

---

### 8. AI Model / Brain
**Problem:** Choosing which AI model powers the agent — affects capability, cost, speed, and reasoning quality.
**Solution:** Anthropic Claude (primary) via API
**Cost:** Pay-per-token. Typical session ~$0.10-0.50. Claude Sonnet 4.6 is current default.
**Setup complexity:** Low
**Status:** Live ✅
**Why this over alternatives:** Claude has the best instruction-following, longest context window for multi-session work, and most reliable behavior for business operations. Steve tops up API credits as needed.
**Alternatives considered:**
- OpenAI GPT-4o — excellent, used for image gen and TTS; slightly less consistent on long-context business tasks
- Google Gemini — strong, free tier available; viable alternative if cost becomes a concern
- DeepSeek — very cheap, good reasoning; privacy considerations for business use
- Grok (xAI) — newer, good for real-time info; less battle-tested for agent work
**Ava integration:** Native — this is what runs Ava. OpenAI API also in credentials.env for specific tasks (image gen, TTS).
**Notes:** API key management: Anthropic console.anthropic.com. Low-balance alert cron pending (low priority). OpenAI key also active for TTS (gpt-4o-mini-tts, Nova voice).

---

### 9. Invoicing / Accounting
**Problem:** Tracking income, expenses, invoices, and P&L across multiple businesses without paying for enterprise accounting software.
**Solution:** Wave Accounting (MRM + Level 19); QuickBooks (Integrity Energy Systems — stays)
**Cost:** Wave: free. QuickBooks: ~$30-50/mo (Integrity keeps it, others switching)
**Setup complexity:** Low (Wave), Medium (QuickBooks already set up)
**Status:** Planned 🔄 (Wave switch for MRM + L19 pending)
**Why this over alternatives:** Wave is genuinely free for invoicing, accounting, and basic reporting — no feature limitations for small business use. No reason to pay QuickBooks $30-50/mo for MRM and Level 19 when Wave handles it.
**Alternatives considered:**
- QuickBooks — keeping for Integrity (Kevin's team uses it, switching would cause disruption); too expensive for MRM/L19
- FreshBooks — $17-55/mo, not worth it
- Xero — $13-70/mo, overkill
**Ava integration:** Wave has an API (GraphQL) — Ava can pull invoice status, create invoices, read transaction history. Full integration planned when Wave accounts are live.
**Notes:** Switch MRM + Level 19 to Wave. Integrity Energy stays on QuickBooks — Kevin's team is set up on it and disruption isn't worth the savings.

---

### 10. Automation / Workflow Builder
**Problem:** Building automated workflows that connect multiple services (email triggers, CRM updates, YouTube processing, content pipelines) without custom code for every connection.
**Solution:** n8n Cloud (Pro)
**Cost:** $60/mo (10K executions/month)
**Setup complexity:** Medium-High
**Status:** Live ✅ (2,545 workflows audited; active workflows running)
**Why this over alternatives:** n8n is self-hostable, has 400+ integrations, and unlike Zapier/Make doesn't charge per task — it charges per execution (a workflow run). Much cheaper at volume. Open source so no vendor lock-in risk.
**Alternatives considered:**
- Zapier — $19-99/mo but charges per task, expensive at volume, less flexible
- Make (Integromat) — good alternative, similar pricing model to n8n; n8n preferred because we're already set up
- Custom Python/scripts — Ava can do this but n8n is better for recurring automations that need a UI and monitoring
**Ava integration:** N8N_API_KEY in credentials.env. Ava can trigger workflows, read execution status, and create simple workflows via API.
**Notes:** N8N_BASE_URL + N8N_API_KEY in credentials.env. Glass Fruit ASMR workflow near-ready. YouTube factory for Christina pending.

**⚙️ n8n Build Standards (mandatory — applied to all workflows):**
1. **Credentials go in n8n's credential store** — never hardcoded in HTTP headers, body, or passed via webhook payload. Use `httpHeaderAuth` or the appropriate credential type. Creates one managed secret vs. a scattered breakpoint.
2. **Use Manual or Schedule triggers by default** — only use Webhook triggers when an external system genuinely needs to initiate the workflow. Webhooks require an external caller to pass the right data; manual/schedule triggers are self-contained and don't break if a caller changes.
3. **No workflow should depend on a caller passing secrets** — if a key needs to change, it changes in one place (the credential store), not everywhere it was hardcoded.
4. **Minimize external dependencies per node** — each node that calls an external API should authenticate via stored credential, not inline expressions pulling from prior nodes.
5. **Test via manual trigger before activating** — run execution from n8n UI before enabling on schedule/webhook.

**Why this matters:** The Email Drip Test workflow failed (401) because it was pulling the GHL API key from the webhook payload. The caller passed an invalid key. Switching to a stored credential fixed it instantly and removed the external dependency entirely. (2026-03-31)

---

### 11. YouTube Transcription
**Problem:** Getting transcripts from YouTube videos for Rich's research queue and content analysis — without getting blocked by YouTube's IP restrictions.
**Solution:** Supadata API
**Cost:** $17/mo (3,000 credits/month)
**Setup complexity:** Low
**Status:** Planned 🔄 (decided 2026-03-30 — account setup pending)
**Why this over alternatives:** VPS IP is blocked by YouTube for direct transcript fetching. Supadata routes around this cleanly. No Google account required. No maintenance. API key only.
**Alternatives considered:**
- Direct YouTube API (yt-dlp / youtube-transcript-api) — blocked by YouTube on VPS IPs
- Google Cloud YouTube Data API — requires Google account, complex OAuth, and still may be blocked
- Manual copy-paste — not scalable for Rich's queue of 20+ videos
**Ava integration:** Simple REST API — pass a YouTube URL, get transcript back. Ava uses this for Rich's research queue and any YouTube content analysis.
**Notes:** Sign up at dash.supadata.ai using ava@maxresultsmedia.com. $17/mo, ease over price — confirmed by Steve. Setup pending.

---

### 12. Payment Processing
**Problem:** Accepting payments online for products and services (AI CoS setup fees, Business Refresh monthly subscriptions, consulting).
**Solution:** Stripe
**Cost:** 2.9% + $0.30 per transaction (no monthly fee)
**Setup complexity:** Low
**Status:** Live ✅
**Why this over alternatives:** Stripe is the industry standard for developer-integrated payments. Clean API, excellent documentation, immediate access to funds (2-day payout). Already set up.
**Alternatives considered:**
- PayPal — higher fees, worse developer experience, more disputes
- Square — better for in-person, weaker for online subscriptions
- Wave Payments — free processing possible but limited integration options
**Ava integration:** Full Stripe API. STRIPE_PUBLISHABLE_KEY + STRIPE_SECRET_KEY (live) in credentials.env. Ava can create payment links, check payment status, manage subscriptions.
**Notes:** Live keys in credentials.env — handle carefully. MRM account.

---

### 13. Document Storage / Shared Workspace
**Problem:** Storing files that both Steve and Ava need access to — without relying on Google Drive (blocked) or paying for Dropbox.
**Solution:** Syncthing (same as #7 — dual-purpose)
**Cost:** Free
**Setup complexity:** Medium (one-time)
**Status:** Live ✅
**Why this over alternatives:** See entry #7. Syncthing solves both "agent-to-human file sync" and "shared document storage" in one tool.
**Alternatives considered:**
- Google Drive — blocked (Steve's Gmail suspended)
- Dropbox — unnecessary cost when Syncthing is free and more private
- OneDrive — being set up for Christina; may expand to Steve in future
**Ava integration:** Direct filesystem access to /data/syncthing-workspace/.
**Notes:** All project files, SOPs, templates, knowledge base live here. Watchdog cron keeps it running.

---

### 14. MLS Property Offers
**Problem:** Sending automated MLS offers to listing agents at scale for real estate acquisitions — without manually searching and emailing one by one.
**Solution:** AcquireFlow API
**Cost:** Free for Steve (direct relationship with Cameron Enck who built it); $600/signup affiliate opportunity
**Setup complexity:** Low (API key already working)
**Status:** Live ✅
**Why this over alternatives:** Cameron built this specifically for the creative finance community. Steve has free access. No comparable alternative exists at this price point.
**Alternatives considered:**
- PropStream offer tools — limited automation, more manual
- REI Reply / BatchLeads — cold outreach focused, not MLS offer automation
- Custom build — would take months; AcquireFlow already does it
**Ava integration:** Full API. ACQUIREFLOW_API_KEY in credentials.env. Ava can search properties, create campaigns, send offers, read agent replies, track pipeline. Base URL: https://acquireflow-ai-dashboard-v7.onrender.com/api/v1
**Notes:** Cameron's PSA contract template pending (he's sending it). Steve needs to define offer criteria: target markets, property types, price ranges. Start at 20-30 offers/day, scale up.

---

### 15. Political Campaign Data
**Problem:** Finding and enriching political campaign contact data — incumbency status, cash on hand, race activity, filing info — for PMB outreach targeting.
**Solution:** FEC API (Federal Election Commission)
**Cost:** Free (api.data.gov)
**Setup complexity:** Low
**Status:** Live ✅
**Why this over alternatives:** It's the official source. All campaign finance data is public by law. Free, comprehensive, reliable.
**Alternatives considered:**
- Paid political data vendors — expensive, often just repackaging FEC data
- Manual FEC website — not scalable
**Ava integration:** FEC_API_KEY in credentials.env. Ava has used this to enrich 621 PMB contacts with cash on hand, race status, and priority tiers.
**Notes:** FEC_API_KEY in credentials.env (Steve has it). api.data.gov key. Use for PMB targeting and enrichment.

---

### 16. SMS / AI Voice (After Hours)
**Problem:** Small business clients miss calls after hours. Calls = revenue. An AI that answers, takes messages, books appointments, and answers questions can recover significant lost business.
**Solution:** Vapi
**Cost:** ~$0.10-0.15/min actual call time; pass-through billing to clients
**Setup complexity:** Medium
**Status:** Planned 🔄 (Tier 5 upsell in Business Refresh)
**Why this over alternatives:** Vapi is purpose-built for AI voice agents. Clean API, low latency, easy to configure with custom prompts. Cost is usage-based so it scales — Ava bills through to clients.
**Alternatives considered:**
- Twilio + custom AI — more work to build, similar end result
- Bland.ai — comparable, slightly less mature ecosystem
- ElevenLabs + custom telephony — overkill for this use case
**Ava integration:** API available. Ava can create phone numbers, configure agents, read call transcripts. Key integration point for Business Refresh Tier 5.
**Notes:** Pass-through billing model — client pays for their usage, not a flat fee. $97-197/mo upsell to clients. High-value for home services, restaurants, salons.

---

### 17. Website Builder for Client Sites
**Problem:** Building client websites that can be generated, customized, and deployed programmatically — at scale, for Business Refresh.
**Solution:** Netlify + HTML templates (custom built)
**Cost:** Included in Netlify Pro ($19/mo flat — see entry #2)
**Setup complexity:** Low per site (once templates are built)
**Status:** Live ✅ (9 templates built 2026-03-31)
**Why this over alternatives:** HTML templates + Netlify = zero per-site cost, fully automatable, Ava deploys via CLI. Christina designs templates once, Ava executes forever.
**Alternatives considered:**
- Duda — Christina's platform for manual builds. NOT for API/automated work. Duda API is expensive and not suited for programmatic site generation at scale.
- WordPress — server management overhead, security issues, not automatable
- Squarespace/Wix — no useful API for programmatic creation
- Webflow — powerful but $$$, not automatable at this scale
**Ava integration:** Full. Ava generates HTML from templates (find-and-replace placeholders), deploys via Netlify CLI, gets a live URL in seconds. NETLIFY_TOKEN in credentials.env.
**Notes:** Templates at /data/syncthing-workspace/projects/business-refresh/templates/ (9 total — 3 per category). Duda = Christina's domain only. Never use Duda for automated/API work.

---

### 18. TTS / Agent Voice
**Problem:** The agent needs to respond with voice (not just text) for a natural conversation experience on Telegram and other channels.
**Solution:** OpenAI gpt-4o-mini-tts, Nova voice, 1.4x speed, warm Irish accent
**Cost:** Per-character billing via OpenAI API (very low — fractions of a cent per message)
**Setup complexity:** Low (configured in OpenClaw)
**Status:** Live ✅
**Why this over alternatives:** Nova voice is natural, warm, and distinctly not robotic. 1.4x speed keeps it snappy without feeling rushed. OpenAI TTS quality is excellent at this price point.
**Alternatives considered:**
- ElevenLabs — better voice customization but $22+/mo for API access; evaluating Mistral Voxtral (free open-weight) as potential replacement for Christina's YouTube channels
- Google TTS — flat, robotic
- Amazon Polly — cheap but lower quality
**Ava integration:** Native via OpenClaw TTS tool. OPENAI_API_KEY in credentials.env.
**Notes:** For Christina's YouTube channels — evaluate Mistral Voxtral (free, open-weight) as ElevenLabs replacement when building n8n YouTube factory.

---

### 19. Code Versioning
**Problem:** Storing scripts, automation code, and project files in version control so nothing is lost and changes can be tracked.
**Solution:** GitHub
**Cost:** Free (public repos) / $4/mo (private repos)
**Setup complexity:** Low
**Status:** Live ✅
**Why this over alternatives:** GitHub is the standard. No evaluation needed.
**Alternatives considered:** None worth documenting.
**Ava integration:** GITHUB_TOKEN + GITHUB_USERNAME in credentials.env. Ava can push/pull code, create repos, manage files via API.
**Notes:** GITHUB_TOKEN in credentials.env.

---

### 20. Deal Evaluation / Property Comps
**Problem:** Quickly estimating ARV and validating wholesaler deal numbers without paying for expensive data subscriptions.
**Solution:** Zillow + Redfin (free, web scrape / public data)
**Cost:** Free
**Setup complexity:** Low
**Status:** Live ✅ (used manually; automation pending)
**Why this over alternatives:** Zillow and Redfin are free, current, and cover most US markets. Sufficient for quick gut-checks on wholesaler ARV claims.
**Alternatives considered:**
- Propstream ($99/mo) — evaluate when deal volume justifies it; has MLS comps, skip tracing, and list building that Zillow/Redfin don't
- BatchLeads — similar to Propstream
- MLS direct access — requires license or brokerage relationship
**Ava integration:** Ava can scrape Zillow/Redfin for basic comp data. No paid API needed at current volume.
**Notes:** Upgrade to Propstream when bird dog volume hits 10+ deals/month evaluated. $99/mo is justified at that point.

---

## PROCESSES

---

### 21. A/B Testing Landing Pages
**Problem:** Knowing which landing page copy converts better without guessing or running tests on separate audiences.

**Process:**
1. Build Version A and Version B as separate HTML files (e.g. `follow.html` and `follow-b.html`)
2. Add Plausible tracking script to both with `data-domain` set to the site domain
3. Add variant prop to both: `plausible('pageview', { props: { variant: 'A' } })` on load
4. Add conversion event to both: `plausible('Signup', { props: { variant: 'A' } })` on form submit
5. Pass `variant` parameter to backend capture function so it's logged in GHL
6. Configure Netlify split test: in netlify.toml or via Netlify UI, set root path to split 50/50 between the two files
7. Send all traffic to one URL — Netlify splits it invisibly

**Tools used:** Netlify Pro + Plausible Analytics
**Status:** Set up 2026-03-31 for /follow (A) vs /follow-b (B)
**Notes:** Plausible account still needs to be created by Steve. One URL to share everywhere — no manual link rotation needed.

---

### 22. Email Harvesting / CRM Building from Inbox
**Problem:** Years of business contacts buried in email inboxes with no CRM records — building it manually would take weeks.

**Process:**
1. Use Microsoft Graph API to scan all mail folders — metadata only (no email body reading yet)
2. Extract every unique sender email address (deduplicate)
3. Pull ONE email per unique sender (the first/intro email — has name, title, company, phone in signature)
4. Send to AI for extraction: name, company, title, phone, 1-sentence summary of who they are
5. Push all records to GHL with source tags and contact notes
6. Total cost at 2,913 contacts: $5.24 in AI API credits. Time: ~3 hours.

**Tools used:** Microsoft Graph API + Claude API + GHL API
**Status:** Completed 2026-03-29 (2,913 Level 19 contacts pushed)
**Notes:** This process can be run for any new business inbox. The key insight: read one email per person, not all emails — reduces AI cost by ~95%.

---

### 23. Bird Dog Deal Distribution
**Problem:** Wholesalers send deals that don't fit Steve's buy box — evaluating them, matching to buyers, and coordinating the handoff is manual and time-consuming.

**Process:**
1. Steve gets wholesaler to add ava@level19homes.com to their deal list
2. Deal arrives → Ava extracts: address, asking price, ARV, repairs, deal type, market
3. Ava pulls independent comps (Zillow/Redfin), gut-checks wholesaler numbers
4. Ava searches GHL for buyers whose buy box matches (market, property type, price range, deal type)
5. Ava Telegrams Steve: deal summary + matched buyers + recommendation (send / hold / pass)
6. Steve approves → Ava reaches out to wholesaler for JV agreement (if not already signed)
7. Ava sends clean deal summary to matched buyer (without wholesaler contact info)
8. If buyer is interested → Ava coordinates intro, tracks in GHL
9. If deal closes → wholesaler pays bird dog fee per JV agreement
10. Ava updates buyer score in GHL (deals_sent, deals_closed)

**Tools used:** ava@level19homes.com (M365 Graph), GHL L19, Zillow/Redfin, Dropbox Sign (JV agreement), Telegram
**Status:** In Progress 🔄 — templates built, waiting for first wholesaler to be added
**Notes:** JV agreement is perpetual — one signature covers all future deals with that wholesaler. Fee comes from wholesaler's side (split from their fee), not markup to buyer. See /data/syncthing-workspace/projects/bird-dog/ for all templates.

---

### 24. Build-in-Public Content System
**Problem:** Creating, organizing, and scheduling a 28-day content campaign across Facebook — without losing track of what's been posted, what's next, and what the URLs are.

**Process / Stack:**
1. Posts written as .md files in `openclaw-service/build-in-public-posts/`
2. Content calendar in `openclaw-service/content-calendar.md` — dates, post order, type, file reference
3. HTML review doc (`ALL-POSTS-FORMATTED.html`) for reading all posts in formatted view
4. ManyChat: "SETUP" keyword in Facebook comments → auto-DM with landing page link
5. Landing page: Netlify-hosted (`follow.html` / `follow-b.html`) — captures name + email → GHL
6. A/B test: Netlify 50/50 split, Plausible variant tracking (see Process #21)
7. GHL Level 19: all signups tagged `ai-cos-follow-along`

**Tools used:** Netlify, Plausible, ManyChat, GHL, Syncthing (file sync)
**Status:** In Progress 🔄 — content done, ManyChat live, Plausible setup complete
**Notes:** First post goes out April 1, 2026. Origin Story post goes first.

**⚠️ ManyChat Limitations (confirmed March 31, 2026):**
- ManyChat comment triggers ONLY work on posts made directly to a Facebook Page — NOT in Facebook Groups
- ManyChat CANNOT build or modify automation flows via API — flows must be built manually in the UI
- ManyChat can only send messages to existing subscribers via API (push data), not to new people
- Group posts: if Steve posts in FB Groups, comment triggers will NOT fire — must direct people to ava@level19homes.com manually or in the post itself
- Do NOT consider ManyChat a solution for any problem involving Facebook Groups, group engagement, or API-driven flow creation

---

### 25. Agent Preset Distribution
**Problem:** Getting a pre-configured AI agent setup (SOUL.md, MEMORY.md, SOPs, operating rules) onto a client's fresh OpenClaw install — without manual file uploads or terminal commands.

**Process (Option C — confirmed working):**
1. Package all preset files into a .zip
2. Host the .zip on Netlify (free, permanent URL)
3. Client pastes one message into their agent's chat: "Download and install my preset package from [URL]"
4. Agent downloads the zip, extracts files to workspace, confirms done
5. Client sends: "Run your first-run setup"
6. Agent introduces itself and begins onboarding conversation

**Tools used:** Netlify (zip hosting), OpenClaw workspace
**Status:** Live ✅ — confirmed working with Christina 2026-03-29
**Preset URL:** https://aicoo-by-ava.netlify.app/preset-package-v1.zip
**Notes:** No terminal, no file manager, no technical knowledge required. One message, full install. This is the core of the AI CoS product delivery.

---

*Last reviewed: 2026-03-31 | Next review: 2026-04-01 (monthly) | 🔴 REVIEW NEEDED tags: none*

---

### 26. Commercial Loan Deal Intake & Referral System
**Problem:** Deal referrals come in via email in every possible format — some complete, some missing half the info. Need a standardized intake that works regardless of how the deal was presented, and a consistent package to send to lenders.

**Process / Stack:**
1. Deal email arrives at ava@level19homes.com
2. Ava sends initial acknowledgment (template in deal-intake-template.md)
3. Ava fills deal intake template with whatever info was provided
4. If gaps exist → send gap follow-up email listing exactly what's missing
5. Once complete → review deal math (LTV, LTC, equity) for red flags before submitting
6. Submit to appropriate lender with completed deal sheet
7. Send deal submitted confirmation to broker/borrower
8. Add broker + borrower to Level 19 GHL with tags: commercial-loan-referral, columbia-referral, broker, borrower

**Tools used:** ava@level19homes.com (M365 Graph), Level 19 GHL, deal-intake-template.md
**Files:** /data/syncthing-workspace/projects/columbia-fund/deal-intake-template.md
**Status:** Active ✅ — first deal in progress (Theresa Davis Lyon / Freddie Mitchell)
**Notes:**
- Always check deal math before submitting — flag inverted LTV/ARV to broker first
- Mike Columbia (Midpoint Capital Partners) = commercial focus, ground-up construction OK, single SFH is borderline
- First-position lenders vs gap/second-position lenders are completely different capital sources — clarify which is needed before routing

---

### 27. Build-in-Public Content System (Full Stack)
**Problem:** Running a 28-day build-in-public campaign across Facebook, Discord, WhatsApp, email, and SMS — with different content tiers for each channel and a subscriber email list that needs to work for both early and late joiners.

**Process / Stack:**
1. **Social (FB/Discord/WhatsApp):** Short tease posts → CTA drives to email signup at /follow
2. **Email (GHL drip):** Full meaty version of each post — more detail, behind-the-scenes, real numbers
3. **SMS (GHL):** Short alert only — "new update just dropped, check your email"
4. **Landing page:** https://aicoo-by-ava.netlify.app/follow → 50/50 split test (C vs D via Edge Function)
5. **Late signup handling:** CATCHUP trigger link → 2 emails/day until current
6. **Feedback loop:** Every email footer has "Email Ava → ava@level19homes.com" → replies logged in testimonials.md → feature requests → callout posts
7. **Testimonials:** /data/syncthing-workspace/openclaw-service/testimonials.md

**Tools used:** Netlify (Edge Function split test), Plausible (analytics), GHL (email + SMS drip), ava@level19homes.com
**Files:** /data/syncthing-workspace/openclaw-service/
**Status:** Ready to launch ✅ — first post April 1, 2026
**Key decisions locked:**
- Challenge framing: "using what I've built" (not "using only AI")
- $10K challenge Day 3 → upgrade to $100K/60 days if/when $10K is hit
- Marriage post → Week 3 minimum
- Service ask → Day 28, written live based on real results
- ManyChat ONLY works on Page posts, not groups — group strategy uses email-in-post-copy

**⚠️ GHL implementation notes:**
- Use trigger links (not reply-text parsing) for SMS opt-in and CATCHUP
- Standard footer on ALL emails: Ava contact line + human unsubscribe copy
- GHL cannot read inbound email reply bodies natively

---

---

### 28. AI Agent + CRM + Email Sync (The "Always-Updated Loop")
**Problem:** An AI agent handles deals, contacts, and communications across email — but without a closed loop, the CRM goes stale, tokens get wasted re-reading old emails, and nothing is reliably up to date.

**Solution:** Connect the agent's email account (Microsoft 365 / Outlook) directly to GoHighLevel so all sent/received emails auto-log to the contact record. Pair with a GHL Opportunities pipeline + webhook so deal stages sync back to the agent's memory files in real time.

**The Module (3 components):**

**Component 1 — Email ↔ GHL Sync (two-way)**
- Go to: GHL → Settings → Email Services → Connect Mailbox
- Connect the agent's Microsoft 365 / Outlook account
- All emails sent from and received at that address will auto-log to the matching contact's conversation timeline in GHL
- Result: The agent can check GHL to see full email history instead of scanning Outlook — saves tokens, prevents duplicate outreach, keeps contact records complete

**Component 2 — Deal Pipeline in GHL Opportunities**
- Create a pipeline with stages matching the business's deal flow (e.g., Intake → Gathering Info → Submitted → Term Sheet → Closed / Dead)
- Add custom fields for deal-specific data (Loan Ask, ARV, LTV, Docs Received, etc.)
- Agent moves deals through stages in real time — GHL becomes the live source of truth, not a markdown file
- Tags keep contacts categorized (buyer, lender, deal type, geography)

**Component 3 — Webhook → Agent Memory Sync**
- Set up a GHL webhook: trigger = Opportunity Stage Changed
- Webhook fires to the agent's endpoint when a deal moves stages
- Agent auto-updates its deal files / memory — no manual logging required
- Result: Files stay current without the agent having to remember to update them

**Deployment checklist (per new business/agent):**
1. Agent has a business email address (M365/Outlook or Gmail)
2. GHL sub-account exists for that business
3. Connect mailbox in GHL Settings → Email Services
4. Build pipeline + stages + custom fields in GHL Opportunities
5. Create tags relevant to that business's contacts
6. Set up webhook (Opportunity Stage Changed → agent endpoint)
7. Agent starts logging all contacts to GHL and moving deals through pipeline

**Applies to:**
- Level 19 Homes (ava@level19homes.com + L19 GHL) ✅ — being implemented April 2026
- Max Results Media (ava@maxresultsmedia.com + MRM GHL) — queue for implementation
- Political Media Buyers (ava@politicalmediabuyers.com + PMB GHL) — queue for implementation
- Any future AI CoS client running OpenClaw + GHL

**Why this is a reusable module:**
Every business that has an AI agent handling email + deals benefits from this exact stack. It's not business-specific — it's a pattern. Agent email + GHL pipeline + webhook = always-updated loop. Apply it anywhere.

**Tools used:** Microsoft 365 / Outlook (Graph API), GoHighLevel (CRM, pipeline, webhooks), OpenClaw (agent runtime)
**Status:** Template ✅ — first implementation in progress (Level 19, April 2026)
**Cost:** Included in existing GHL subscription + M365 license

---

---

### 29. AI Video Course Creation (Camera-Averse Experts)
**Problem:** Subject-matter experts with decades of knowledge will never get on camera. The creator economy was built for performers — these people are locked out. Traditional course production takes weeks per module.

**Solution:** HeyGen AI avatar production + Claude knowledge extractor workflow
**Cost:** HeyGen premium tier (required for client-facing work — check current pricing); Claude already in stack
**Setup complexity:** Medium — one-time avatar creation per expert, then repeatable per module
**Status:** Filed 💡 — not yet implemented. Full brief at `/data/syncthing-workspace/projects/ai-course-agency/STATUS.md`
**Source:** https://youtu.be/m-rZ45KCL_I (analyzed 2026-04-28, real production case)

**Workflow:**
1. Expert films 2-3 min consent video → HeyGen clones voice + likeness (premium tier)
2. Knowledge extractor skill (Claude) interviews expert via voice notes → pulls curriculum, examples, edge cases
3. AI drafts full module scripts in expert's voice from transcribed notes
4. **Human edits for pacing/pauses/emphasis — NON-SKIPPABLE** — AI doesn't pause; a teacher does
5. Scripts rendered in HeyGen with branded backgrounds + icon sets → full module
6. Edit the script → entire video refflows (no re-recording — huge for compliance/SOP update clients)

**Best client types (in order of value):**
- Corporate training / SOP clients — recurring revenue as content updates
- Camera-averse experts with premium one-on-one rates — obvious upsell
- Course localization (existing course → multiple languages) — underserved, fast delivery
- Regulated fields (doctors, lawyers, financial advisors) — compliance updates = recurring work

**Connection to existing work:**
- Knowledge extraction is structurally identical to IES SOP interviews (Kevin/Beth Q&A)
- MRM natural upsell for existing clients who are subject-matter experts
- Steve's own expertise (media buying, real estate, lending) = first potential product

**Alternatives considered:** Traditional video production (5-10x slower, requires camera time)

---

## 📦 n8n Workflow Library (Check Before Building)

**Rule:** Before building any new n8n workflow from scratch, check this library first. Many common patterns are already templated.

**Source spreadsheet (200+ workflows):**
https://docs.google.com/spreadsheets/d/1C5PPS9uEHhhZ6-94hXapC8IZYRQLULoGMYJ32-N0BLQ/htmlview

**Downloaded workflows (ready to import):**
`/data/syncthing-workspace/n8n-workflows/` — 20 curated workflows + README with index

**How to import:** n8n Cloud → Workflows → New → ⋯ menu → Import from File → select JSON → reconnect credentials → test before activating.

**Top picks by use case:**
- Lead qualification → `property-lead-qualification.json`
- YouTube transcripts/summaries → `youtube-summaries-transcripts-gemini.json`
- Multi-platform social publishing → `blotato-multiplatform-social-publisher.json`
- Email autoresponder with approval → `ai-email-autoresponder-with-approval.json`
- SEO blog from Notion → `notion-triggered-seo-content-publisher.json`
- n8n backup to GitHub → `n8n-workflow-backup-to-github.json`

See `n8n-workflows/README.md` for the full index.
