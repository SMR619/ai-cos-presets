# Tools Knowledge Base
**Purpose:** A searchable database of proven tools that solve specific problems. Before recommending or implementing any tool, search here first.

**For AICOS Agents:** Your agent has access to this knowledge base. When you need to solve a problem, the agent will search this database to find tools already vetted and proven.

**How to use:**
1. Search by **Problem** column — what are you trying to solve?
2. Search by **Use Cases** column — what's your scenario?
3. Read the **Verdict** column — is this actively used, under investigation, or not relevant?
4. Read the **Notes** column — setup, constraints, context

---

## LEGEND

- **Verdict:** 
  - `ACTIVE` = actively in use, battle-tested
  - `STRONG FIT` = fits your needs perfectly, recommended
  - `INVESTIGATE` = promising, worth evaluating
  - `WATCHLIST` = monitor, compare alternatives
  - `NOT RELEVANT` = skip for now
- **Own/Use:** 
  - ✅ = in active use
  - 🔄 = planned/in setup
  - ❌ = not subscribed/not using

---

## QUICK-START REFERENCE

**Need to send business emails at scale?**
→ Microsoft Graph API (or Instantly.ai for cold outreach)

**Need to automate complex workflows?**
→ n8n (active solution)

**Need to manage CRM + sales pipeline?**
→ GoHighLevel

**Need to build an AI agent?**
→ FlowiseAI (self-host, free)

**Need to transcribe YouTube videos?**
→ Supadata API

**Need to scrape web data?**
→ Scrapy (free, Python) or Outscraper (pay-as-you-go)

**Need to deploy a website?**
→ Netlify (unlimited sites for $19/mo)

**Need to handle payments?**
→ Stripe

**Need to sign contracts?**
→ Dropbox Sign

**Need to make/receive AI voice calls?**
→ Vapi (agent builder) + Telnyx (carrier)

**Need to analyze videos for insights?**
→ NotebookLM (free, AI answers questions from uploaded video/documents)

---

## FULL TOOLS DATABASE

### INFRASTRUCTURE & HOSTING

| Tool | Problem It Solves | Use Cases / Scenarios | Cost | Verdict | Notes |
|------|------------------|----------------------|------|---------|-------|
| **Hostinger VPS** | Server/host for AI agents and web apps | Running AI agents, hosting OpenClaw, deploying web apps, managing cron jobs | ~$10/mo | ACTIVE | 2 vCPU, 8GB RAM, 96GB disk. Standard setup for AI agent operations. |
| **OpenClaw** | Manages AI agents, sessions, crons, Telegram, tools | Building AI assistants, scheduling automations, multi-step workflows, agent orchestration | Free (self-hosted) | ACTIVE | Open-source agent framework. No vendor lock-in. Runs on any VPS. |
| **Netlify Pro** | Host unlimited client sites, landing pages, serverless | Building landing pages, deploying static sites, A/B testing campaigns, hosting SaaS frontends | $19/mo flat | ACTIVE | One flat fee, unlimited sites. Deploy via CLI. Serverless functions included. |
| **GitHub** | Store scripts, automation code, track changes | Version control for code, storing automation scripts, managing repositories, tracking project history | Free / $4/mo private | ACTIVE | Industry standard. Git-based workflow. |
| **Syncthing** | Sync files between VPS and PC automatically | Real-time file syncing across devices, backup automation, collaborative file editing | Free | ACTIVE | Open-source, decentralized. Privacy-safe. |
| **Vercel** | Deploy Next.js + modern JS apps | Building Next.js applications, rapid frontend prototyping with AI, edge function deployment | Free / $20/user/mo | WATCHLIST | Use Netlify for current static site needs. Evaluate if going full Next.js. |

### AI MODELS & REASONING

| Tool | Problem It Solves | Use Cases / Scenarios | Cost | Verdict | Notes |
|------|------------------|----------------------|------|---------|-------|
| **Anthropic Claude API** | Core reasoning, writing, analysis, agent intelligence | Strategic analysis, complex reasoning, multi-step planning, content writing, research | Usage-based (~$10-30/mo) | ACTIVE | Sonnet is the default. Haiku for cost-sensitive tasks. Opus for deep reasoning. |
| **OpenAI API** | Voice transcription and text-to-speech | Voice message transcription, AI voice replies, audio content generation, TTS automation | ~$2-10/mo | ACTIVE | Whisper (transcription) and Nova voice (TTS) models. Industry standard. |
| **Deep Infra** | One API for image gen, transcription, TTS, video, embeddings | Budget transcription, low-cost image generation, text-to-video conversion, embedding calculations | Pay-per-use (cheaper than OpenAI) | INVESTIGATE | Open-source models at low cost. Good for: transcription, embeddings, budget inference. |
| **Brave Search API** | Search the web without sharing data with Google | Web research, competitive intelligence, finding resources, fact checking | Free (2K searches/mo) | ACTIVE | Privacy-first. No tracking. Good research foundation. |
| **FlowiseAI** | Visually build LLM workflows, RAG pipelines, multi-agent systems | Building chatbots, creating RAG pipelines, orchestrating multi-step AI workflows, low-code agent design | Free (self-hosted) / $35-65/mo cloud | STRONG FIT | Open-source. Self-host on VPS = zero cost. "n8n for AI." Highly recommended. |
| **NotebookLM** | AI answers questions from YOUR documents (not hallucinations) | RAG over business docs, deal analysis from files, cited answers from uploaded PDFs, video analysis | Free | STRONG FIT | Google product. Upload docs → AI answers with citations. Relevant for: deal packets, lender research, video/article analysis. |
| **Obsidian** | Persistent AI memory, local markdown knowledge graph | AI agent memory system, personal KB, Zettlekasten, wiring agents to context | Free | STRONG FIT | Local markdown files = privacy safe. Works with AI via MCP. Backbone of agent memory systems. |

### COMMUNICATION & OUTREACH

| Tool | Problem It Solves | Use Cases / Scenarios | Cost | Verdict | Notes |
|------|------------------|----------------------|------|---------|-------|
| **Telegram Bot** | Steve-to-Ava messaging on mobile | Mobile agent communication, voice commands, lightweight status updates, quick messaging | Free | ACTIVE | Allowlisted to specific users only. Voice transcription via Whisper. |
| **Microsoft Graph API (M365)** | Send emails from real business addresses | Sending automated business emails, managing email accounts via API, email automation workflows | ~$6-12/user/mo (already paying) | ACTIVE | Sends from branded email addresses. Saves to Sent Items. Professional. |
| **GoHighLevel (GHL)** | CRM, email/SMS, pipelines, automations across all businesses | Managing sales pipelines, automating customer follow-ups, tracking leads, email/SMS campaigns | $97-297/mo | ACTIVE | All-in-one CRM + automation platform. Good for sales teams and service delivery. |
| **Instantly.ai** | High-volume cold outreach without burning root domain | Bulk cold email campaigns, lead generation at scale, multi-touch outreach sequences | ~$37/mo | PLANNED | Phase 2 expansion. Use subdomain, not root domain. |
| **Vapi.ai** | AI voice agent for inbound/outbound calls | Automating phone support, outbound lead calling, appointment scheduling via voice, complex IVR routing | ~$0.05-0.15/min | ACTIVE | AI voice agent platform. Works with any CRM. Complex routing capabilities. |
| **Telnyx** | VoIP carrier — provides phone numbers and routes calls | Providing phone numbers, routing calls to AI agents, call infrastructure | ~$1/mo per number + $0.004/min | ACTIVE | 3x cheaper than Twilio. Works with Vapi. Standard carrier integration. |
| **ManyChat** | Automated DMs from Facebook Page comment triggers | Instagram automation, Facebook comment reply sequences, social media lead generation, DM automation | Free / $15/mo | ACTIVE | Limited to Page posts, not groups. Good for Instagram engagement automation. |

### BUSINESS TOOLS & PAYMENTS

| Tool | Problem It Solves | Use Cases / Scenarios | Cost | Verdict | Notes |
|------|------------------|----------------------|------|---------|-------|
| **Dropbox Sign (HelloSign)** | Legally binding contract signatures, loan docs, JV agreements | Contract signing workflows, loan document execution, JV agreement signing, digital signature automation | ~$15-25/mo | ACTIVE | API available. Legal. Professional. |
| **Stripe** | Accept payments, subscriptions, one-time charges | Accepting online payments, recurring subscriptions, one-time charges, payment automation | 2.9% + $0.30/transaction | ACTIVE | Industry standard. Webhook support. Subscription management. |
| **Wave Accounting** | Track income, expenses, invoices | Business accounting, expense tracking, invoice generation, financial reporting | Free | PLANNED | Free accounting software. Good for MRM + L19. |
| **QuickBooks** | Accounting for teams | Small business accounting, tax preparation, multi-user access, industry-specific tracking | ~$30-50/mo | ACTIVE | Standard for team-based accounting. Integration with Stripe. |
| **Plausible Analytics** | Privacy-first analytics + A/B test variant tracking | Website traffic tracking, A/B test variant analysis, GDPR-compliant analytics, landing page metrics | Free / $9/mo | ACTIVE | No cookies. No tracking. GDPR compliant. Good for landing pages. |
| **Microsoft Clarity** | Free heat maps, session recordings, drop-off analysis, dead click detection | Conversion optimization, funnel analysis, user behavior tracking, session recording analysis | Free | ACTIVE | Microsoft product. Install on every page. CRO insights. |

### AUTOMATION & WORKFLOWS

| Tool | Problem It Solves | Use Cases / Scenarios | Cost | Verdict | Notes |
|------|------------------|----------------------|------|---------|-------|
| **n8n Cloud (Pro)** | Automate processes connecting 400+ services | Multi-step integrations, connecting tools, data transformation, workflow orchestration | $60/mo (10K executions) | ACTIVE | Battle-tested. 2,500+ live workflows. Never hardcode credentials. |
| **Apify** | Pre-built scraping and automation actors | Lead scraping, web monitoring, data extraction without writing code, competitor analysis | Free (5 runs/mo) / $49/mo Starter | INVESTIGATE | Marketplace of pre-built automations. Integrates with n8n. ~$50/mo for needed use cases. |
| **Make.com** | Visual automation connecting 1000+ apps | Simple automations, quick workflows, alternative to n8n for simpler use cases | Free (1K ops/mo) / $9-16/mo | WATCHLIST | Direct n8n competitor. Simpler UI, slightly less powerful. Good alternative if n8n becomes pain point. |
| **Activepieces** | Open-source Zapier alternative | Self-hosted automation, cost-free workflows, n8n alternative | Free (open source) | WATCHLIST | Open-source. Self-hostable on VPS = zero cost. Monitor as alternative. |
| **Supabase** | PostgreSQL database + auth + storage as a service | App backends, structured data storage, organizing knowledge bases | Free (500MB) / $25/mo Pro | ACTIVE | Already in use. SQL-based. Scalable. Good for data-heavy applications. |
| **Airtable** | Structured data storage with API access | Lead tracking, call logging, deal pipeline, structured data for AI tool calls | Free (1K records) / $10-20/mo per user | INVESTIGATE | Spreadsheet-like with API. More flexible than Google Sheets. Good for structured data. |

### REAL ESTATE & DATA

| Tool | Problem It Solves | Use Cases / Scenarios | Cost | Verdict | Notes |
|------|------------------|----------------------|------|---------|-------|
| **AcquireFlow API** | Send automated MLS offers at scale | Automating property offers, bulk MLS submissions, real estate lead follow-up, offer automation | Varies (project-based) | ACTIVE | Purpose-built for real estate. Direct MLS integration. |
| **FEC API** | Political campaign finance data | Political campaign research, donor targeting, campaign finance analysis, lead enrichment | Free | ACTIVE | Federal Election Commission data. Free API. Use for political research. |
| **Zillow / Redfin** | Quick ARV estimates, gut-check wholesaler numbers | Property valuation, comparable market analysis, real estate research, deal analysis | Free | ACTIVE | Industry standard. Free estimates. Web-based. |

### CONTENT & MEDIA

| Tool | Problem It Solves | Use Cases / Scenarios | Cost | Verdict | Notes |
|------|------------------|----------------------|------|---------|-------|
| **Supadata API** | Get YouTube transcripts without IP blocks | YouTube video analysis, content research, transcript extraction, video summarization | $17/mo | ACTIVE | YouTube blocks direct scraping. Supadata bypasses this. Use for all YouTube research. |
| **Outscraper** | Scrape Google Maps business data — name, phone, email, address, reviews | Lead generation, local business research, competitor analysis, Google Maps scraping | Free first 500/mo; $3/1K up to 100K | STRONG FIT | Pay-as-you-go. 100M+ records. Essentially free for small volumes (~$1.50-3 per city at scale). |
| **Slybroadcast** | Drop voicemails directly into inboxes without ringing | Cold voicemail campaigns, lead prospecting, bulk outreach automation, ringless voicemail testing | Pay-as-you-go: $10/100 voicemails | INVESTIGATE | Used by experienced outreach pros. SOC2/HIPAA compliant. Zapier integration. Good for testing. |
| **Figma** | Professional design tool for mockups, templates, prototypes | Website design, app mockups, design collaboration, UI/UX prototyping | Free Starter / $16/mo Professional | INVESTIGATE | Free tier is powerful for solo use. Industry standard for design teams. |
| **Seedance (ByteDance)** | Native 4K AI video generation + upscaling | Creating video ads from product images, upscaling existing footage, faceless video production | Pay-per-use | STRONG FIT | Text→Video, Image→Video. Native 4K (not upscaled). High quality. |
| **Descript** | Edit video by editing transcript text | Podcast/video editing, transcription, clipping content for social media repurposing | Free (1hr transcription) / $12-24/mo | INVESTIGATE | Edit video like document text. Overdub AI voice. Good for content repurposing. |

### WEB DEVELOPMENT & APP BUILDING

| Tool | Problem It Solves | Use Cases / Scenarios | Cost | Verdict | Notes |
|------|------------------|----------------------|------|---------|-------|
| **Next.js** | React framework with SSR, routing, API routes, edge functions | Building dynamic web applications, server-side rendering, API development, edge computing | Free (open-source) | WATCHLIST | Foundation for future dynamic web apps. Not needed for current static sites. |
| **Node.js** | JavaScript runtime | Running JavaScript applications, backend development, scripting, automation runtime | Free (open-source) | ACTIVE | Already running everywhere. Foundation of modern dev stacks. |
| **FlowiseAI** | Visually build LLM workflows and multi-agent systems | Building chatbots, creating RAG pipelines, orchestrating multi-step AI workflows | Free (self-hosted) / $35-65/mo cloud | STRONG FIT | Open-source. Install on VPS = free. Best for agent-based applications. |
| **Lovable / Base44** | UI-first web app builder for rapid prototyping | Rapid web app prototyping, visual app development, low-code web application building | ~$20-50/mo | INVESTIGATING | Currently evaluating. Chat-to-code approach. Fast iteration. |
| **Cursor** | AI Code Editor — code with AI inside VS Code | AI-assisted development, code generation, debugging, pair programming with AI | Free / $20/mo Pro | WATCHLIST | Industry standard for AI-assisted coding. 67% Fortune 500 adoption. |
| **Hermes Agent V0.15+** | Free open-source persistent AI agent | Agent swarms, parallel task execution, persistent memory via Obsidian, kanban task boards | Free (open source) | INVESTIGATE | Open-source alternative to OpenClaw. Agent swarms (parallel execution). VPS-compatible. |

### WEB SCRAPING & DATA EXTRACTION

| Tool | Problem It Solves | Use Cases / Scenarios | Cost | Verdict | Notes |
|------|------------------|----------------------|------|---------|-------|
| **Scrapy** | Production-grade Python web scraping framework | Web scraping at scale, data extraction, lead generation, competitor monitoring | Free (open-source) | INVESTIGATE | Free, powerful. Ava can write spiders. VPS-native. Good for large-scale scraping. |
| **BeautifulSoup** | Python HTML parsing library | HTML parsing, web scraping with Python, data extraction from HTML/XML | Free (open-source) | INVESTIGATE | Foundation of Python web scraping. Used in Ava's scripts. Simple and powerful. |

---

## AFFILIATED TOOLS (Revenue Opportunities)

These tools have affiliate programs available:

- **AcquireFlow API** — $600/signup affiliate
- **Hostinger** — Referral commissions available
- **Netlify** — Agency/referral program
- **Stripe** — Not a traditional affiliate, but good partner relationship
- **Posted.com** — Creator platform (pay-per-result, no affiliate)

---

## KNOWN GAPS / TOOLS UNDER EVALUATION

| Problem | Status | Tool Being Evaluated |
|---------|--------|----------------------|
| AI phone agent (voice) | ✅ Active | Vapi + Telnyx |
| AI agent builder (visual) | ✅ Active | FlowiseAI |
| Workflow automation | ✅ Active | n8n |
| Database storage | ✅ Active | Supabase |
| Web scraping | ✅ Evaluating | Scrapy vs Outscraper |
| Email outreach | 🔄 Planned | Instantly.ai |

---

## HOW YOUR AGENT USES THIS

When you ask your agent to solve a problem:

1. **Agent searches this database** — "Find me a tool for X"
2. **Agent checks Verdict** — Is it ACTIVE or STRONG FIT?
3. **Agent reads Notes** — Setup, cost, constraints
4. **Agent uses the tool** — Or reports "This needs human approval" or "This isn't the right tool for this problem"

**You can always update this database** — Find a new tool? Tell your agent "Add this tool to my Tools Knowledge Base" with the problem it solves and when to use it.

---

## WANT TO ADD A TOOL?

Format:
```
**[Tool Name]** — [Problem] | [Use Case] | [Cost] | [Verdict] | [Notes]
```

Examples:
- **Zapier** — Automate workflows | Connecting 5000+ apps | $20-99/mo | WATCHLIST | Evaluating vs n8n
- **Airtable** — Structured data storage | Lead pipelines, deal tracking | $10-20/mo per user | INVESTIGATE | More flexible than sheets, less code than databases

---

**Last Updated:** 2026-06-04
**Maintained By:** Your AI CoS Agent
**Format:** Searchable markdown table (indexed for agent access)
