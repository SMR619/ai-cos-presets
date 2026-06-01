# Tools Master Database
**Maintained by:** Ava  
**Last Updated:** 2026-05-31  
**Purpose:** The first place we look when a problem needs a tool solution. Before recommending anything new, check here.

> **How to use this:** Search by Category or Problem column. If the problem is already solved, use the existing solution. Only evaluate alternatives if there's a specific gap.

---

## LEGEND
- **Verdict:** STRONG FIT | INVESTIGATE | WATCHLIST | NOT RELEVANT | ACTIVE (already in use)
- **Own/Use:** ✅ Active | 🔄 Planned/Setup | ❌ Not subscribed
- **Use Cases / Scenarios:** Real-world situations or problem types where this tool applies. Written as searchable phrases (e.g. "building a mobile app", "designing a paywall", "automating email outreach"). Used to surface tools even when they seem not currently relevant — search this column first when brainstorming solutions to a new problem.
- **Affiliate:** "Yes" | "No" | "Unknown" — whether the tool has an affiliate program
- **Affiliate Research Date:** When we last researched affiliate availability
- **Commission / Structure:** How affiliates are compensated (%, flat rate, CPA, etc.)
- **Affiliate Link/Code:** Our active affiliate link, code, or program ID (if applicable)

> **Search tip:** When working on a new idea or project, search this file for keywords from the problem (e.g. "paywall", "email", "landing page") — the Use Cases column is how you find tools that apply even if they weren't built for our exact business.
> **Affiliate tip:** Every tool we use should have an "Affiliate" column checked. Research affiliate programs during tool evaluation. See `ACTIVE_AFFILIATES.md` for our live affiliate accounts and current earnings.

---

## FULL DATABASE

| Tool | Category | Problem It Solves | Use Cases / Scenarios | Cost | Verdict | Own/Use | Affiliate | Aff. Research Date | Commission/Structure | Aff. Link/Code | Notes |
|------|----------|------------------|----------------------|------|---------|---------|-------|
| **INFRASTRUCTURE & HOSTING** | | | | | | | |
| Hostinger VPS | Infrastructure | Server/host for all tools and agents | Running AI agents, hosting OpenClaw, deploying web apps, managing cron jobs | ~$10/mo | ACTIVE | ✅ | 2 vCPU, 8GB RAM, 96GB disk. Ava lives here. |
| OpenClaw | Agent Runtime | Manages AI agents, sessions, crons, Telegram, tools | Building AI assistants, scheduling automations, multi-step workflows, agent orchestration | Free (self-hosted) | ACTIVE | ✅ | Current version pinned. Don't auto-update. |
| Netlify Pro | Website Hosting | Host unlimited client sites, landing pages, serverless | Building landing pages, deploying static sites, A/B testing campaigns, hosting SaaS frontends | $19/mo flat | ACTIVE | ✅ | One flat fee, unlimited sites. Deploy via CLI. A/B testing built in. |
| GitHub | Code Versioning | Store scripts, automation code, track changes | Version control for code, storing automation scripts, managing repositories, tracking project history | Free / $4/mo private | ACTIVE | ✅ | GITHUB_TOKEN in credentials.env. |
| Syncthing | File Sync | Sync files between VPS and Steve's PC automatically | Real-time file syncing across devices, backup automation, collaborative file editing | Free | ACTIVE | ✅ | Watchdog cron active. /data/syncthing-workspace is the shared folder. |
| Vercel | Deployment/Hosting | Deploy Next.js + modern JS apps; AI-assisted frontend (v0) | Building Next.js applications, rapid frontend prototyping with AI, edge function deployment | Free / $20/user/mo | WATCHLIST | ❌ | Use Netlify for current needs. Switch if we go full Next.js. v0 free tier worth testing. |
| **AI MODELS & REASONING** | | | | | | | |
| Anthropic Claude API | AI Brain | Core reasoning, writing, analysis, agent intelligence | Strategic analysis, complex reasoning, multi-step planning, content writing, research | Usage-based (~$10-30/mo) | ACTIVE | ✅ | Sonnet 4.6 default. Hard monthly cap set in console.anthropic.com. |
| OpenAI API (Whisper + TTS) | Voice AI | Transcribe voice messages; Ava's voice (Nova) | Voice message transcription, AI voice replies, audio content generation, TTS automation | ~$2-10/mo ($30 cap) | ACTIVE | ✅ | gpt-4o-mini-tts, Nova voice, 1.4x speed, warm Irish accent. |
| Deep Infra | AI Models (multi-modal, budget) | One API for image gen, image edit, audio transcription, TTS, text-to-video, embeddings — open-source models at low cost | Budget transcription, low-cost image generation, text-to-video conversion, embedding calculations | Pay-per-use (fraction of OpenAI pricing) | INVESTIGATE | ❌ | Built-in OpenClaw 4.27 provider. Llama, Mistral, Qwen + more. Do NOT use for client-facing content (quality gap vs Claude). Good candidates: transcription (IES calls), embeddings (memory search), image gen (social posts). Sign up at deepinfra.com, add API key to OpenClaw. Flagged 2026-04-30. |
| Brave Search API | Web Research | Search the web without sharing data with Google | Web research, competitive intelligence, finding resources, fact checking | Free (2K searches/mo) | ACTIVE | ✅ | Rich uses for research. Ava uses for general lookups. |
| FlowiseAI | AI Agent Builder | Visually build LLM workflows, RAG pipelines, multi-agent systems | Building chatbots, creating RAG pipelines, orchestrating multi-step AI workflows, low-code agent design | Free (self-hosted) / $35-65/mo cloud | STRONG FIT | ❌ | Open-source. Install on VPS — zero recurring cost. "n8n for AI." Self-host immediately. |
| **COMMUNICATION** | | | | | | | |
| Telegram Bot | Agent Communication | Steve-to-Ava messaging on mobile | Mobile agent communication, voice commands, lightweight status updates, quick messaging | Free | ACTIVE | ✅ | Allowlisted to Steve ID only. Voice transcription via Whisper. |
| Microsoft Graph API (M365) | Email Sending | Send emails from real business addresses (MRM, L19, PMB) | Sending automated business emails, managing email accounts via API, email automation workflows | ~$6-12/user/mo (already paying) | ACTIVE | ✅ | Sends from ava@maxresultsmedia.com, ava@level19homes.com, etc. Saves to Sent Items. |
| GoHighLevel (GHL) | CRM / Automation | CRM, email/SMS, pipelines, automations across all businesses | Managing sales pipelines, automating customer follow-ups, tracking leads, email/SMS campaigns | $97-297/mo | ACTIVE | ✅ | MRM, L19, PMB accounts active. Agency Pro needed for Business Refresh sub-accounts. |
| Instantly.ai | Cold Email Outreach | High-volume cold outreach without burning root domain | Bulk cold email campaigns, lead generation at scale, multi-touch outreach sequences | ~$37/mo (Growth) | PLANNED | 🔄 | Phase 2 Business Refresh outreach. Use subdomain, not root MRM. |
| ElevenLabs | Voice Generation | High-quality AI voice cloning and generation | YouTube voiceover automation, AI voice cloning, faceless video production, text-to-speech at scale | Free (10K chars) / $5-22/mo | PLANNED | 🔄 | Evaluate Mistral Voxtral (free) first for Christina's YouTube factory. |
| Vapi.ai | AI Phone Agent | AI voice agent for inbound/outbound calls | Automating phone support, outbound lead calling, appointment scheduling via voice, complex IVR routing | ~$0.05-0.15/min | ACTIVE | ✅ | Account created 2026-04-24. VAPI_API_KEY in credentials.env. Best for: complex routing, non-GHL CRMs (e.g. IES/Method), custom logic, emergency escalation. |
| GoHighLevel Voice AI (native) | AI Phone Agent (GHL-native) | Claude-powered voice agent built natively into GHL — answers calls, qualifies leads, books appointments, updates pipeline. No external tools. | Qualifying sales calls, lead intake automation, appointment booking, customer service automation | Included in GHL plan (per-minute usage) | STRONG FIT | ✅ | GHL added Claude Sonnet/Haiku as selectable models in Agent Studio (April 2026). Use for: MRM clients, Level 19 lead intake, PMB, AI CoS service delivery. All-in-one: call → qualify → book → CRM update in one platform. No webhooks needed. NOT for IES (Method CRM, needs custom routing). Business Refresh Phase 2 upsell: $200-500/mo/client MRR. AI CoS Module: standard "AI phone employee" deliverable. |
| Retell AI | AI Phone Agent | AI voice/phone agents — inbound, outbound, 24/7 | 24/7 phone support, outbound campaigns, customer service automation, complex call routing | ~$0.13-0.17/min all-in | WATCHLIST | ❌ | Direct Vapi competitor. Claude/GPT LLM flexibility. Monitor but no need to evaluate now — GHL native voice covers most use cases. |
| ManyChat | Social Automation | Automated DMs from Facebook Page comment triggers | Instagram automation, Facebook comment reply sequences, social media lead generation, DM automation | Free / $15/mo | ACTIVE | ✅ | ⚠️ Only works on Page posts, NOT groups. Cannot build flows via API. |
| **BUSINESS TOOLS** | | | | | | | |
| Dropbox Sign (HelloSign) | E-Signatures | Legally binding contract signatures, loan docs, JV agreements | Contract signing workflows, loan document execution, JV agreement signing, digital signature automation | ~$15-25/mo | ACTIVE | ✅ | API available. Already subscribed. No reason to switch. |
| Stripe | Payment Processing | Accept payments, subscriptions, one-time charges | Accepting online payments, recurring subscriptions, one-time charges, payment automation | 2.9% + $0.30/transaction | ACTIVE | ✅ | Live keys in credentials.env. MRM account. |
| Wave Accounting | Invoicing/Accounting | Track income, expenses, invoices for MRM + L19 | Business accounting, expense tracking, invoice generation, financial reporting | Free | PLANNED | 🔄 | Switching MRM + L19 from QuickBooks. QuickBooks stays for IES (Kevin's team). |
| QuickBooks | Accounting | IES accounting — Kevin's team uses it | Small business accounting, tax preparation, multi-user access, industry-specific tracking | ~$30-50/mo | ACTIVE | ✅ | Keep for IES only. MRM + L19 switching to Wave. |
| Plausible Analytics | Website Analytics | Privacy-first analytics + A/B test variant tracking | Website traffic tracking, A/B test variant analysis, GDPR-compliant analytics, landing page metrics | Free / $9/mo | ACTIVE | ✅ | Used for Business Refresh landing page A/B tests. No cookies, GDPR compliant. |
| Microsoft Clarity | Funnel / CRO Analytics | Free heat maps, session recordings, drop-off analysis, dead click detection. Connect to Claude via MCP for plain-English funnel queries. | Conversion optimization, funnel analysis, user behavior tracking, session recording analysis | Free | ACTIVE | ✅ | Install on EVERY page we build. SOP: sops/sop-microsoft-clarity-cro.md. Active on: AI CoS, MyBuyBox, Small Business Refresh client sites. |
| **AUTOMATION & WORKFLOWS** | | | | | | | |
| n8n Cloud (Pro) | Workflow Automation | Automate processes connecting 400+ services | Multi-step integrations, connecting tools, data transformation, workflow orchestration | $60/mo (10K executions) | ACTIVE | ✅ | 2,545 workflows. Never hardcode credentials. Use stored credential type. |
| Pipedream | Developer Automation | Code-native event-driven automation (Zapier alternative for devs) | Custom code workflows, event-driven automation, serverless workflow automation, integration development | Free (3 workflows) / $19-149/mo | WATCHLIST | ❌ | n8n is the active solution. Pipedream = alternative if n8n becomes a pain point. Better for complex code-native workflows. |
| **REAL ESTATE & DATA** | | | | | | | |
| AcquireFlow API | MLS Property Offers | Send automated MLS offers at scale | Automating property offers, bulk MLS submissions, real estate lead follow-up, offer automation | Free (Steve's direct relationship) | ACTIVE | ✅ | Cameron Enck built it. $600/signup affiliate opportunity. |
| FEC API | Political Data | Political campaign finance data for PMB outreach targeting | Political campaign research, donor targeting, campaign finance analysis, lead enrichment | Free (api.data.gov) | ACTIVE | ✅ | FEC_API_KEY in credentials.env. Used for PMB contact enrichment. |
| Zillow / Redfin | Property Comps | Quick ARV estimates, gut-check wholesaler numbers | Property valuation, comparable market analysis, real estate research, deal analysis | Free | ACTIVE | ✅ | Upgrade to Propstream ($99/mo) when bird dog volume hits 10+ deals/month. |
| **CONTENT & MEDIA** | | | | | | | |
| Supadata API | YouTube Transcription | Get YouTube transcripts without VPS IP blocks | YouTube video analysis, content research, transcript extraction, video summarization | $17/mo (3K credits) | ACTIVE | ✅ | API key in credentials.env (SUPADATA_API_KEY). Use for all YouTube transcript pulls. VPS IP blocked by YouTube directly — always use Supadata first. |
| Outscraper | Lead Scraping | Scrape Google Maps business data — name, phone, email, address, reviews | Lead generation, local business research, competitor analysis, Google Maps scraping | Free first 500/mo; $3/1K up to 100K; $1/1K after | STRONG FIT | ❌ | Pay-as-you-go, no subscription needed. 100M+ records, 249 countries. Essentially free at Business Refresh scraping volumes (~$1.50-3/city). First 500 records always free. Integrate via API or web UI. |
| Slybroadcast | Ringless Voicemail | Drop voicemails directly into inboxes without ringing — for cold outreach | Cold voicemail campaigns, lead prospecting, bulk outreach automation, ringless voicemail testing | Pay-as-you-go: $10/100, $40/500, $400/10K. Only charged for delivered drops. | INVESTIGATE | ❌ | Used by Chris Koerner live for Business Refresh-style outreach. SOC2/PCI/HIPAA compliant. Zapier/API integrations. Good for testing. Upgrade to VoiceDrop or Drop Cowboy at scale for better delivery rates + AI voice cloning. |
| VoiceDrop | Ringless Voicemail (AI) | AI-powered ringless voicemail with voice cloning + callback system | AI voice prospecting, ringless voicemail at scale, voice cloning campaigns, callback automation | From $95/mo (1K drops) | WATCHLIST | ❌ | Better analytics, AI voice cloning, built-in callback system vs Slybroadcast. Evaluate when Business Refresh Phase 2 outreach scales beyond testing. |
| Drop Cowboy | Ringless Voicemail | Ringless voicemail with Smart Delivery™ — higher carrier compatibility | Bulk voicemail campaigns, improved delivery rates, carrier-optimized voicemail drops | Varies | WATCHLIST | ❌ | Highly rated delivery rates. Compare vs Slybroadcast before committing to any RVM platform at volume. |
| Figma | UI/UX Design | Professional design tool for mockups, templates, prototypes | Website design, app mockups, design collaboration, UI/UX prototyping | Free Starter / $16/mo Professional | INVESTIGATE | ❌ | Free starter is powerful for solo use. Check if Christina is already using it. If not, set her up. |
| Mobbin | UI/UX Reference | Library of 400K+ real app screenshots for design inspiration | Design inspiration, competitor UX analysis, app interface research, design system reference | $10/mo (Pro, annual) | WATCHLIST | ❌ | Useful when actively designing. Easy to justify at $10/mo during active design projects. |
| **WEB DEVELOPMENT** | | | | | | | |
| Next.js | Web Framework | React framework with SSR, routing, API routes, edge functions | Building dynamic web applications, server-side rendering, API development, edge computing | Free (open-source) | WATCHLIST | ❌ | Foundation for future dynamic web apps. Not needed for current static sites. |
| Node.js | Runtime | JavaScript runtime — foundation for OpenClaw, n8n, and more | Running JavaScript applications, backend development, scripting, automation runtime | Free (open-source) | ACTIVE | ✅ | Already running on VPS (v22.22.1). Not a choice — it's a dependency. |
| **AI APP BUILDERS** | | | | | | | |
| Hercules | AI App Builder | Build full-stack apps (SaaS, internal tools, eCommerce) by chatting with AI | Full-stack app development, SaaS building, internal tool creation, eCommerce setup | Free tier / Paid tiers available | INVESTIGATE | ❌ | 100K+ users. All-in-one backend included. Compare against Lovable/Base44. Test free tier first. |
| Lovable / Base44 | AI App Builder | UI-first web app builder for rapid prototyping | Rapid web app prototyping, visual app development, low-code web application building | ~$20-50/mo | INVESTIGATING | 🔍 | Currently evaluating. Ava writes prompts, Steve pastes into UI. |
| CreateAnything (Anything) | AI App Builder | Build web + iOS + Android apps from prompts | Cross-platform app development, mobile app generation, web app building, multi-platform deployment | Free / $20-50/mo (Pro) | WATCHLIST | ❌ | Cross-platform app generation including mobile. Compare with Hercules for specific use cases. |
| Rork | Mobile App Builder | Build native React Native / Expo mobile apps from prompts | Native mobile app development, App Store deployment, iOS/Android app building | $20-200/mo (no free tier) | WATCHLIST | ❌ | Best for actual App Store mobile apps. No free tier = barrier to testing. |
| Caffeine AI | AI App Builder | Build decentralized apps on ICP blockchain via chat | Blockchain app development, Web3 application building, decentralized app creation | ~$20-60/mo | NOT RELEVANT | ❌ | Blockchain deployment not needed for our use cases. Skip. |
| Durable | AI Website Builder | 30-second AI website generation for small businesses | Rapid website generation, competitive intelligence, AI-powered landing pages, small business websites | Free / $25/mo | WATCHLIST | ❌ | Competitive intelligence for Business Refresh. Their free tier shows where market is commoditizing. |
| **AI ASSISTANTS & TOOLS** | | | | | | | |
| Sintra AI | AI Business Assistant | Suite of 12 specialized AI helpers for business tasks | Business task automation, specialized AI helpers, business process automation | $15-48/mo | NOT RELEVANT | ❌ | Redundant — Claude + n8n + GHL covers everything Sintra does, better. |
| **WEB SCRAPING** | | | | | | | |
| Scrapy | Web Scraping | Production-grade Python web scraping framework | Web scraping at scale, data extraction, lead generation, competitor monitoring | Free (open-source) | INVESTIGATE | ❌ | Ava can write and run Scrapy spiders directly on VPS. Immediate value for PMB, L19, Business Refresh lead gen. |

---

## KNOWN GAPS / UNDER EVALUATION

| Problem | Status | Notes |
|---------|--------|-------|
| AI phone agent (voice) | ✅ Active | Vapi selected 2026-04-24. Account live. Telnyx for carrier. First agents: IES after-hours + Level 19 intake. |
| AI agent builder (visual) | ❌ Not started | FlowiseAI self-host is the move — free, VPS-compatible |
| Email harvesting automation | ✅ Done | Process #22 in PLAYBOOK.md — completed for L19 (2,913 contacts) |
| Propstream (property data) | Evaluate at 10+ deals/month | $99/mo justified when bird dog volume hits that level |
| Clay (AI prospecting) | 📋 Watch | $149/mo — evaluate when Business Refresh scales to Phase 2 |

---

## ACTIVE MONTHLY SPEND (ESTIMATED)

| Tool | Cost |
|------|------|
| Hostinger VPS | ~$10 |
| Netlify Pro | $19 |
| Anthropic Claude API | ~$10-30 |
| OpenAI API (Whisper + TTS) | ~$2-10 |
| n8n Cloud Pro | $60 |
| GoHighLevel | $97-297 |
| Dropbox Sign | ~$15-25 |
| Vapi | ~$0-20/mo (usage) | pay-per-minute, minimal for initial agents |
| Telnyx | ~$1-5/mo | phone number(s) + call minutes |
| OpenRouter | ~$0-10/mo | model cost testing, fallback routing |
| **TOTAL (range)** | **~$214-487/mo** |

---

## TOOLS BY USE CASE (QUICK REFERENCE)

**Need to send email at scale?** → Instantly.ai (outreach) or M365 Graph (personal)  
**Need to automate workflows?** → n8n (active)  
**Need to build an AI agent?** → FlowiseAI (self-host, free)  
**Need to make/receive phone calls with AI?** → Vapi (active) + Telnyx (carrier)  
**Need to scrape web data?** → Scrapy (free, Ava writes it)  
**Need to deploy a website?** → Netlify (active)  
**Need to design a website/template?** → Figma (free starter)  
**Need to build an app without code?** → Hercules (test free tier first)  
**Need to build a mobile app?** → Rork ($20/mo) or CreateAnything  
**Need to process payments?** → Stripe (active)  
**Need to sign contracts?** → Dropbox Sign (active)  
**Need to track contacts/deals?** → GoHighLevel (active)  
**Need political campaign data?** → FEC API (free, active)  
**Need property comps?** → Zillow/Redfin (free) → Propstream at volume  
**Need YouTube transcripts?** → Supadata API ($17/mo, planned)  
**Need UI/design inspiration?** → Mobbin ($10/mo when actively designing)  

---

---

## 🎥 AI Video Generation

### Seedance (ByteDance)
- **What:** Native 4K AI video generation + upscaling. Text-to-video, image-to-video, video-to-video, upscale existing footage.
- **Why it matters:** Generates natively in 4K (not upscaled) — materially better quality than competitors at 720p/1080p
- **Pricing:** Pay-per-use only. No monthly fee. Only charged per generation. API available.
- **Access:** seedance (ByteDance - access via supported AI platforms) | playground.seedance (ByteDance - access via supported AI platforms)
- **Best for:** Creating video ads from product images, upscaling existing low-quality video, faceless YouTube channel video generation
- **Status:** Monitor — explore when MRM client video creative or ad production needs grow. Christina flagged for ad work April 2026.
- **Added:** 2026-04-18

---

---

## 🎙️ Voice Agent Infrastructure (Added 2026-04-24)

### Vapi
- **What:** AI voice agent platform — build inbound/outbound phone agents
- **Account:** Created 2026-04-24. VAPI_API_KEY in credentials.env.
- **Carrier:** Telnyx (see below)
- **Use cases:** IES after-hours agent, Level 19 intake agent, MRM B2B outreach agent
- **Status:** ACTIVE

### Telnyx
- **What:** VoIP carrier — provides phone numbers and routes calls
- **Cost:** ~$1/mo per number + $0.004/min (vs Twilio's $0.014/min — 3x cheaper)
- **Account:** Created 2026-04-24. TELNYX_API_KEY in credentials.env.
- **Status:** ACTIVE

### OpenRouter
- **What:** Multi-model AI gateway — 353 models including Hunyuan (free), DeepSeek, Llama, Claude
- **Account:** Created 2026-04-24. OPENROUTER_API_KEY in credentials.env.
- **Use:** Cost reduction testing — route cheaper tasks to lower-cost models
- **Notable:** tencent/hy3-preview available FREE on OpenRouter — replaces Tencent direct signup
- **Status:** ACTIVE

---

### OpenBB (Free Bloomberg Terminal) — FUTURE USE
- **Status:** Documented for future use. Not setting up now — unclear ROI vs API cost/time. Revisit when MidPoint deal volume increases and we need real-time market data in Ava's workflow.
- **When to revisit:** When Steve says "I need macro context for this deal" more than once a week, or when MidPoint starts requiring live data for LP presentations.
- **What:** Open-source financial data platform for analysts and AI agents.
- **URL:** openbb.co | pro.openbb.co
- **Cost:** Free tier + pro plans
- **Setup time:** ~30 min
- **Key capabilities:** FRED data (interest rates, macro), Yahoo Finance, SEC filings, REIT comps, 37 AI analyst personas (Buffett, Munger, etc.), MCP integration with Claude
- **Limitation:** Steve's concern is valid — doesn't want API calls eating credits for no clear reason. OpenBB can pull data without Claude if used standalone, but the AI features require LLM calls.
- **Note:** Not a Bloomberg replacement. No proprietary feeds, no dealer chat.

### OpenBB (Free Bloomberg Terminal)
- **What:** Open-source financial data platform. Free terminal for equity research, macro data, REIT comps, SEC filings, FRED data, AI analyst agents.
- **URL:** openbb.co | pro.openbb.co (browser-based, no install needed)
- **Cost:** Free tier available. Pro plan for advanced features.
- **Use:** MidPoint deal context (interest rates, cap rates, REIT comps), lender market analysis, economic briefings
- **Setup:** Register at pro.openbb.co → connect FRED API key (free) → connect Anthropic API key for AI features → 30 min total
- **AI Features:** Pre-built analyst personas (Buffett, Munger, etc.) — bring your own LLM key
- **Status:** Not yet set up. Evaluate for MidPoint deal analysis.

### Posted.com — Creator Marketing on Autopilot
- **What:** Creator campaign platform. Launch a campaign, creators from their network make videos about your product and post on TikTok/Instagram/YouTube. You pay per result.
- **Payment model:** Set CPM rate ($1/1K views) + optional flat fee ($10/creator). Pay only when content is posted and viewed — zero upfront.
- **Affiliate model alternative:** Can also structure as conversion-based (per sale) if you give creators a unique link — see affiliate tracking section below.
- **Use cases:** AI CoS launches, Owner Stack skill promotion, Level 19 brand awareness in RE community
- **Results from video:** 300 videos submitted, 200K+ views, tracked against Firebase first-time-opens. Running on autopilot.
- **Strategy:** First build organic sales + reviews, then use those as social proof in Posted campaign brief.
- **URL:** posted.com
- **Status:** Researched + recommended. Use after first Owner Stack sales and reviews come in.

### Affiliate Tracking — Options

**Option A: Rewardful** (recommended to start)
- $49/month Starter → handles up to $7,500/month from affiliates
- Stripe native integration — syncs payments automatically
- Affiliate dashboard (affiliates log in, see earnings)
- Custom referral slugs (/ref/[name])
- 14-day free trial
- URL: rewardful.com

**Option B: FirstPromoter**
- Similar to Rewardful; also handles influencer coupon codes alongside links
- $49/month entry
- URL: firstpromoter.com

**Option C: Build Custom** (project for later)
- Supabase + Netlify + Stripe webhooks — already have all components
- Features: unique slugs, GHL contact tagging with referral source, affiliate login dashboard, payout tracking, admin view
- Build time: 20–40 hours
- Value: also solves Steve's existing affiliate tracking gap + sellable as a product
- Project file: `/data/syncthing-workspace/projects/owner-stack/STATUS.md`

**Attribution Policy (locked):**
- Last-click wins within 30-day cookie window
- Per-product: each product has its own attribution (same person can be attributed to different affiliates for different products)
- Same product, same person: only first purchase counts for affiliate credit
- Cookie reset: 30-day window resets on new click
- Fine print: "Affiliate credit earned on first qualifying purchase within 30 days of referral click."

**AI CoS Affiliate Model:**
- 20% commission per AI CoS sale ($997 sale = $199.40 to affiliate)
- Unique slug per creator: myaicos.netlify.app?ref=[creator-slug]
- GHL contacts tagged with referral source on signup
- Dashboard: creator sees clicks, conversions, earnings, payout status
- Payout: monthly, bank transfer or PayPal

### Free Claude Code (Open Source) — FUTURE USE
- **Status:** Documented for future use. Pull back up when building apps, scripts, or web tools.
- **When to revisit:** When Steve says "I want to build [app/website/automation]" — use this before burning Anthropic tokens on coding sessions.
- **What:** Open-source version of Anthropic's Claude Code CLI that routes to any API provider (including free models). Lets you use Claude Code's agentic coding capabilities for free.
- **How it works:** Install from GitHub → configure OurAlpha free API key → run `claude` in terminal → coding agent writes/edits files autonomously
- **Free backend:** OurAlpha (1M token context, free, designed for agentic work)
- **Cost:** $0 to run. Uses free model, not Anthropic.
- **Risk:** OurAlpha is a free service — may rate-limit or change. Quality lower than Claude Sonnet. Good for code, not for reasoning/judgment tasks.
- **Important:** Does NOT affect Ava or OpenClaw. Runs separately as a standalone coding agent.
- **GitHub:** Search "free-claude-code" on GitHub
- **Note:** Steve's rule — don't use for active sessions with Ava. Only for coding/build sessions.

### Mobile App Tech Stack (2026) — COMPLETE BREAKDOWN
- **When to use:** When client or Steve wants to build a mobile app
- **Validated by:** Creator who scaled Puff Count to $45K/month, then a second app to $150K/month
- **Key insight:** Almost all tools are free to start; cost scales with revenue

#### PHASE 1: LEGAL & BUSINESS SETUP
| Tool | Cost | What it does |
|------|------|--------------|
| Doola | Paid | LLC formation + bookkeeping + taxes |
| Termly | Freemium | Auto-generates ToS + Privacy Policy (required for App Store approval) |
| Apple Small Business Program | Free to apply | Reduces Apple's cut from 30% → 15% for apps under $1M revenue. APPLY IMMEDIATELY. |

#### PHASE 2: RESEARCH (validate idea + find marketing angles)
| Tool | Cost | What it does |
|------|------|--------------|
| Sensor Tower | Paid | Spy on any app's downloads, revenue, rankings |
| Google Trends | Free | Validate keyword/topic demand over time |
| Flippa / Acquire.com | Free to browse | Buy/sell app businesses; see what's making money and selling for how much |
| Viral Ad Library | Free | Top-performing ad videos across any app category |
| Facebook Ads Library | Free | All active competitor ads running RIGHT NOW |
| TikTok Ads Library | Free | Same for TikTok |
| TikTok Top Ads | Free | Broader category view of top TikTok ads |
| TikTok Creative Insights | Free | Trending keywords and hashtags to target |

#### PHASE 3: UI DESIGN
| Tool | Cost | What it does |
|------|------|--------------|
| 99designs | Paid per project | Design contest — get dozens of designs, pay only for your favorite |
| Paywall Screens | Paid | Spy on any app's paywall: pricing, revenue estimates, A/B tests they're running |
| Screens.design | Paid | See every screen inside any app; watch full onboarding video; copy to Figma |
| UX Pilot | Freemium | AI app design from wireframes or sketches |
| Stitch (by Google) | Free | AI UI builder from uploaded files or website URL |
| Uizard | Freemium | AI app UI builder |
| Figma | Freemium | Day-to-day design hub; build all screens; drag-and-drop after initial design |
| growth.design | Free | UX case studies on top apps; user psychology courses |

#### PHASE 4: DEVELOPMENT
| Tool | Cost | What it does |
|------|------|--------------|
| Apple Developer Account | $99/yr | Required to publish iOS apps. Includes App Store Connect + Xcode |
| Apple Pre-Order Feature | Free | Accept pre-orders before launch; all convert to installs on launch day |
| Google Play Developer | $25 one-time | Required to publish Android apps |
| Claude Code | API cost | #1 coding AI tool right now for writing/editing code |
| Cursor | Subscription | Another top AI coding tool |
| Roark (Roark Max) | Subscription | Vibe coding MVP tool — one-shots full mobile app MVPs, publishes direct to App Store |
| Firebase (Google) | Freemium | **Primary backend for mobile apps** — database, user auth, analytics, push notifications, Google Ads integration. More standard for mobile than Supabase. |
| Framer | Freemium | Pre-built landing page templates for app marketing pages |
| ThemeForest | Per item | Pre-built, fully developed app templates — buy and customize |
| Upwork | % of freelancer rate | Hire developers, designers. Tip: hire from Eastern Europe — lower cost, high quality |
| ChatGPT | Subscription | General AI assistant during dev |

#### PHASE 5: OPTIMIZATION (scale revenue)
| Tool | Cost | What it does |
|------|------|--------------|
| Superwall | Paid | A/B test paywalls AND onboarding flows without pushing App Store updates. Tests hundreds of variants to find max LTV. |
| RevenueCat | Freemium | Subscription + revenue analytics. Tracks LTV, active subs, churn. Standard for subscription apps. |
| AppsFlyer | Paid (enterprise) | Mobile Measurement Partner (MMP) — tracks installs + sends attribution events back to ad platforms. Required for iOS 14+ paid ads at scale. |
| Adjust | Paid | MMP alternative to AppsFlyer |
| Branch | Freemium | MMP alternative; also handles deep linking |
| Amplitude | Freemium | Product analytics — user behavior, retention dashboards, KPI charts. Build custom dashboards by user segment. |
| App Follow | FREE | ASO tracking, keyword ranking, competitor keyword tracking, auto-reply to App Store reviews. Connect to App Store Connect. Must-have. |

#### PHASE 6: MARKETING & SCALING
| Tool | Cost | What it does |
|------|------|--------------|
| ManyChat | Paid | Auto-DM anyone who comments on your Instagram Reels. "Comment XYZ → get the link." Drives massive engagement + conversions. |
| Tweet Hunter | Paid | X/Twitter post scheduling + auto-DMs. Creator drove 43M impressions, 40K followers via X. |
| TikTok Ads | CPC/CPM | Start here or Meta first; scale to others after |
| Meta Ads | CPC/CPM | Expand to Meta after finding winning TikTok creative |
| Snapchat Ads | CPC/CPM | Expand after scaling TikTok/Meta |
| Beehiiv | Freemium | Email newsletter + automation. Better than Mailchimp. Waitlists, welcome sequences, remarketing. Creator has 26K subscribers. |
| Posted | Pay-per-result | Creator campaign platform. Launch campaigns, creators post about your app, you pay per CPM. 300 videos, 200K views on autopilot. |
| Snabbtik / InDown | Free | Download your own TikToks/Reels for cross-posting to other platforms |
| Appify | Freemium | Pre-built automation and scraping tools. Anything you can imagine is already automated here. |

#### KEY NOTES FOR STEVE
- **Firebase, not Supabase, is the mobile app backend standard.** Supabase is better for web apps.
- **Apple Small Business Program saves 15% on revenue** — apply immediately if ever publishing an iOS app.
- **Start marketing with organic TikTok/Instagram; amplify winners with paid ads** — not the other way around.
- **ManyChat is the Instagram growth cheat code** — also relevant for Christina’s YouTube channels (has Instagram component).
- **Beehiiv > Mailchimp** for app email lists. Could also be used for AI CoS client waitlist.
- **Posted = influencer marketing on autopilot, pay per result** — evaluate for Level 19/MRM campaigns.

- **Status:** Documented for AI CoS clients and future Steve app builds.

---

---

## NEW TOOLS — Added 2026-05-30 (from 21-Video Analysis)

| Tool | Category | Problem It Solves | Use Cases / Scenarios | Cost | Verdict | Own/Use | Notes |
|------|----------|------------------|----------------------|------|---------|---------|-------|
| **Trace Solo** | AI Coding Agent | Background automated AI workflows — set task once, runs forever | Recurring content reports, sentiment tracking, automated research pipelines | Free tier / paid | WATCHLIST | ❌ | By ByteDance (TikTok parent). Free tier genuine. Multi-agent, voice input, Figma integration. Privacy note: Chinese data laws. Do NOT put sensitive business data here. Good for: non-sensitive research, content pipelines. |
| **Hermes AI Agent** | AI Agent (open source) | Free open-source AI coding/task agent | AI coding tasks, agent swarms (parallel multi-agent), kanban task management, team-of-agents orchestration | Free (open source) | INVESTIGATE | ❌ | v0.15 has agent swarms (parallel multi-agent). Kanban board. One-command setup. Compare to OpenClaw for specific use cases. |
| **Obsidian** | Knowledge Base / AI Memory | Persistent AI agent memory via local markdown notes | AI agent memory system, personal knowledge base, connecting agent to context files, Zettlekasten note-taking | Free | STRONG FIT | ❌ | Wires to AI agents for persistent memory. All notes local (privacy-safe). Free. The backbone of agent memory stacks for AI CoS clients. Set up for AI CoS onboarding. |
| **ClickBank** | Affiliate Marketing | Affiliate marketplace — find products paying 50-75% commissions | Affiliate income from YouTube/content channels, passive income streams, finding digital products to promote | Free to join | INVESTIGATE | ❌ | 25+ years old, billions in commissions paid. Relevant for Christina's faceless YouTube channels as affiliate income layer. |
| **RevenueCat** | App Subscriptions | Mobile app subscription management + paywall analytics | App subscription infrastructure, in-app purchase handling, paywall A/B testing, cancellation analysis | Free up to $2.5K MRR / % after | WATCHLIST | ❌ | Used by 115K+ apps. Only relevant if building a mobile app. File away for that future. |
| **Qwen 3.7 Max** | AI Model (budget) | Top-tier coding model at lower cost than Claude | Budget coding tasks, high-volume cron job inference, data processing at scale | API pay-per-use (cheaper than Claude) | WATCHLIST | ❌ | Alibaba's model. Beats GPT 5.5 and Gemini 3.5 Flash on coding benchmarks. Watch as Claude cost alternative for specific automated tasks. |
| **Grok 5** | AI Model | 1.5T parameter coding model trained on Cursor data | High-complexity coding, software engineering tasks | TBD (not released yet) | WATCHLIST | ❌ | XAI/Elon Musk. Trained on Cursor programming data. Expected release ~June 2026. Test when available. |
| **Shipper** | AI App Builder | Build full-stack apps by talking to AI | Full-stack app building via chat, SaaS creation | $25/mo (credits) | WATCHLIST | ❌ | $50K MRR bootstrapped. Compare to Lovable/Base44 currently being evaluated. |
| **ACQ.ai** | AI Advisor (RAG) | Hormozi's AI advisor trained on all his books + advisory notes | Business strategy questions, offer design, pricing, sales — all answered via RAG on proprietary content | Included in $6K bundle | INVESTIGATE | ❌ | Blueprint for how to build a proprietary AI advisor. Our framework database + Ava is building toward this. Reference architecture for AI CoS product. |
| **Token Tracker Dashboard** | Claude Code Analytics | Track Claude Code token usage across sessions | Monitoring AI spend, optimizing prompt efficiency, identifying expensive workflows | Free (open source GitHub repo) | STRONG FIT | ❌ | Free GitHub repo. Give Claude Code the repo, it sets itself up, imports historical token data. Install now. |
| **School** | Paid Community Platform | Host paid communities, courses, and cohorts | Paid community behind offer gate, course delivery, cohort management, alternative to Facebook groups | ~$99/mo | INVESTIGATE | ❌ | Hormozi uses it for $3K/month advisory community. Better than Facebook groups for paid tiers. Evaluate for AI CoS paid community. |

*Last updated: 2026-05-30 by Ava (from 21-video analysis session)*
