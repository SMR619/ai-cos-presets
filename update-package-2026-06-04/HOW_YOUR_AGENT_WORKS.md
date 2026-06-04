# How Your Agent Works — The Foundation Module

## What This Module Is

This module explains the **5 foundation systems** that power every other capability your AI agent provides. 

These aren't tasks you'll do directly. They're the backbone that makes everything else possible.

**Analogy:** Just like a car engine enables the car to go fast, these 5 systems enable your agent to make smart decisions.

---

## The 5 Foundation Systems

Your agent is built on 5 core systems. Together, they provide the context and intelligence that everything else depends on.

### System 1: Memory Architecture

**What it does:**  
Your agent remembers everything about your business, goals, and preferences — so decisions are personalized, not generic.

**How it works:**
Your memory is organized in 3 tiers:

1. **Tier 1 — Active Memory** (`MEMORY.md`)
   - Current situation, active projects, priorities, what you're working on right now

2. **Tier 2 — Domain Knowledge** (Your `wiki/` folder)
   - Your businesses (what they do, revenue, metrics)
   - Your deal structures and red flags
   - Your key relationships
   - Your operating rules and procedures
   - Your communication style and voice

3. **Tier 3 — Historical Context** (Session logs from previous conversations)
   - Patterns in what you do
   - Decisions you've made
   - Results you've achieved
   - How you prefer to work

**Why it matters:**  
Without memory: Agent writes generic emails, makes generic suggestions, doesn't understand your context  
With memory: Agent writes YOUR emails in YOUR voice, makes suggestions aligned with YOUR business, understands YOUR context

**What you provide:**
- Business context (what you do, revenue model, goals)
- Your preferences (how you like to work, your communication style)
- Regular updates (what's changed, lessons learned, new rules)

**Setup checklist:**
- [ ] Read `MEMORY_ARCHITECTURE_SETUP.md`
- [ ] Start filling out your `wiki/` folder (businesses, deals, people, rules, procedures)
- [ ] Update wiki weekly with new lessons and changes

---

### System 2: Operating Rules

**What it does:**  
Your agent has a decision-making framework. It checks "Is this right?" before taking action.

**How it works:**
You document rules about:
- **Financial criteria** — What ROI/returns do you require? What's your max risk?
- **Deal criteria** — What deal structures do you do? What's a dealbreaker?
- **Time allocation** — What gets your time? What doesn't?
- **Communication** — How do you want to be communicated with?
- **Risk tolerance** — What's non-negotiable?
- **Decision authority** — Who decides what? What gets escalated to you?

Before making a decision, agent checks: "Does this align with Steve's rules?"

**Why it matters:**  
Without rules: Agent makes assumptions and mistakes  
With rules: Agent makes decisions aligned with how you think

**Examples of rules:**
- "Require 20% value-add on all deals"
- "Decisions under $50K are yours to make"
- "Always verify before sending emails"
- "Email for async, calls for decisions"

**What you provide:**
- Your decision-making framework (what matters to you)
- Your financial criteria (returns, risk, capital deployment)
- Your deal criteria (what structures you do)
- Your communication preferences
- Your risk tolerance and non-negotiables

**Setup checklist:**
- [ ] Read `OPERATING_RULES_SETUP.md`
- [ ] Document your top 5-10 rules
- [ ] Add them to `wiki/04-rules.md`
- [ ] Share rules with your team

---

### System 3: Framework Library

**What it does:**  
Your agent uses proven thinking patterns and communication formulas instead of guessing.

**How it works:**
Frameworks are organized by type:

- **Communication Frameworks** — How to write persuasively, tell stories, negotiate, handle objections
  - Examples: PAS Framework (Problem-Agitate-Solution), Tactical Empathy, LAPS Sales System
  
- **Business Frameworks** — How to structure offers, price, generate leads, scale
  - Examples: 100M Offers, Deal Analysis Frameworks, Pricing Models
  
- **Operations Frameworks** — How to scale, delegate, build systems
  - Examples: EOS, E-Myth, Traction
  
- **Financial Frameworks** — How to analyze deals, calculate ROI, structure financing
  - Examples: Cap Rate Analysis, Cash-on-Cash Return, Financing Options

When your agent needs to make a decision or communicate:
- It identifies which framework applies
- It uses that framework to structure the solution
- It personalizes the result with your context

**Why it matters:**  
Frameworks are proven methods. Using them means better decisions faster.

**Examples:**
- Writing to a lender? Use Communication Framework + Deal Analysis Framework
- Structuring a partnership? Use 100M Offers Framework + Deal Structure Framework
- Delegating to team? Use Operations Framework + Communication Framework

**What you get:**
- Pre-built frameworks (already in your `frameworks/` folder)
- Frameworks organized by problem type (easy to find the right one)
- Examples of each framework in action

**Setup checklist:**
- [ ] Read `FRAMEWORKS_GUIDE.md`
- [ ] Skim your `frameworks/` folder to see what's available
- [ ] When you learn a new framework, add it to the folder
- [ ] Reference frameworks by name when asking your agent

---

### System 4: Tools Knowledge Base

**What it does:**  
Your agent has a searchable database of proven tools that solve common problems. When you need something built, the agent knows which tools are best.

**How it works:**
The database is organized by **problem**, not by tool:

- Problem: "I need to send automated emails"
  - Agent knows: Microsoft Graph (branded email), Instantly.ai (cold outreach), GHL (CRM-integrated), each with costs/pros/cons

- Problem: "I need to transcribe a video"
  - Agent knows: Supadata for YouTube, Whisper for other videos, Otter for meetings

- Problem: "I need to automate workflows"
  - Agent knows: n8n (active), Make, Zapier, Activepieces, each with different capabilities

- Problem: "I need to build a website"
  - Agent knows: Netlify, Vercel, Next.js, each fits different needs

For each tool:
- What problem it solves
- Use cases and scenarios
- Cost
- Verdict (actively used, recommended, or alternative)
- Setup notes and constraints

**Why it matters:**  
You don't have time to research tools. Agent does. When a need comes up, agent suggests the right tool with cost and implementation path.

**What you get:**
- Searchable tools database (100+ proven tools)
- Organized by problem type
- Current costs and affiliate opportunities
- Known gaps and tools under evaluation
- Agent can research and add new tools

**Setup checklist:**
- [ ] Read `TOOLS_KNOWLEDGE_BASE.md`
- [ ] Skim the database to see what's available
- [ ] When you find a new tool, tell your agent to add it
- [ ] Reference tools by name when asking for recommendations

---

### System 5: Knowledge Base System

**What it does:**  
Your agent learns from everything that happens and organizes lessons so they apply to future situations.

**How it works:**
The knowledge base has 3 tiers:

1. **Raw Input** (research, PDFs, articles, videos, transcripts)
   - Source material — not processed yet

2. **Analyzed Outputs** (extracted insights from research)
   - What you learned from competitor analysis, books, videos, research
   - Organized by topic
   - Actionable and indexed

3. **Extracted Lessons** (patterns and principles you've discovered)
   - "When I do X, Y happens" lessons
   - "This framework works for Z situation"
   - Evidence and examples included

Agent uses lessons to:
- Evaluate new opportunities against what you've learned
- Apply past experience to current situations
- Spot patterns before they become problems
- Suggest strategies based on what worked before

**Why it matters:**  
Without capturing learning: You forget what you learned. Learn same lesson twice.  
With knowledge base: Agent references past learning. You handle similar situations better each time.

**Examples of lessons:**
- "Cold email with personalization gets 3x response vs. template"
- "Deals with 3-month timelines are riskier than 6-month"
- "Customers who implement immediately see 2x better results"
- "Team members hired for culture adapt faster than those hired for skills alone"

**What you get:**
- Organized knowledge folders (outputs, lessons, raw research)
- Search across all your learning
- Agent references lessons when making recommendations
- You build learning compound over time

**Setup checklist:**
- [ ] Read `KNOWLEDGE_BASE_SETUP.md`
- [ ] Explore what's already in your `knowledge/` folder
- [ ] After important projects/research, add findings to outputs/
- [ ] When you notice a pattern, add a lesson to lessons/
- [ ] Update knowledge monthly

---

## How These 5 Systems Work Together

```
Your MEMORY provides context
     ↓
OPERATING RULES ensure good decisions
     ↓
FRAMEWORKS structure thinking + communication
     ↓
TOOLS Knowledge Base provides solutions
     ↓
KNOWLEDGE BASE System captures learning
     ↓
Result: Intelligent, personalized, context-aware agent
```

**Example workflow:**

1. **Situation:** You get a deal opportunity
2. **Memory** reads your wiki → understands your deal criteria
3. **Operating Rules** checks → does this fit your financial requirements?
4. **Framework Library** applies → uses Deal Analysis Framework + Risk Framework
5. **Tools KB** suggests → here are tools for analysis
6. **Knowledge Base** references → you've dealt with similar deals before, here's what happened
7. **Result:** Agent gives you analysis aligned with YOUR criteria based on YOUR experience

---

## What You Provide to Make This Work

| System | You Provide | Benefit |
|--------|-------------|---------|
| Memory | Business context, preferences, updates | Agent understands YOU |
| Rules | Decision framework, financial criteria | Agent makes good decisions |
| Frameworks | Your preferred thinking models | Agent uses proven methods |
| Tools KB | New tools you discover | Always up-to-date toolkit |
| Knowledge Base | Lessons from experience | Agent gets smarter over time |

---

## Setting Up This Foundation

**Get started:**

1. **Week 1:** Read all 5 setup docs
   - `MEMORY_ARCHITECTURE_SETUP.md`
   - `OPERATING_RULES_SETUP.md`
   - `FRAMEWORKS_GUIDE.md`
   - `TOOLS_KNOWLEDGE_BASE.md`
   - `KNOWLEDGE_BASE_SETUP.md`

2. **Week 2:** Fill out your wiki
   - `wiki/01-businesses.md`
   - `wiki/04-rules.md`
   - Add your businesses and top rules

3. **Ongoing:** Feed the systems
   - Update wiki with lessons
   - Add new tools you discover
   - Capture important learning in knowledge/

---

## How Your Agent Explains This To You

When you ask "How do you know that?" or "How did you decide that?", your agent will say something like:

> "I checked your wiki and saw you require 20% value-add (that's your operating rule from 04-rules.md). I used the Deal Analysis Framework (which applies the cap rate analysis method). I referenced the Tools Database to suggest AcquireFlow for MLS integration. This is similar to the deal you mentioned in March — here's what happened then (from your knowledge base). Based on all of this, here's my recommendation."

That's the foundation working. Agent isn't guessing — it's synthesizing YOUR memory, YOUR rules, proven FRAMEWORKS, best TOOLS, and past LEARNING.

---

## Foundation Powers Everything Else

All the other modules depend on this foundation:

- **Email Management** uses Memory + Frameworks + Rules
- **Deal Tracker** uses Memory + Rules + Frameworks + Tools KB + Knowledge Base
- **CRM Sync** uses Memory + Rules + Tools KB
- **Content Creation** uses Memory + Frameworks + Knowledge Base
- **Outreach Support** uses Memory + Frameworks + Tools KB + Knowledge Base
- **Research Brief** uses Frameworks + Tools KB + Knowledge Base
- **Weekly Level-Up** uses Memory + Rules + Frameworks + Knowledge Base

**Without this foundation, those modules wouldn't work.**

With this foundation, those modules are powerful, personalized, and aligned with how you actually work.

---

## Next Steps

1. **Read the 5 setup guides** (start with your learning style — visual skimmer? Read guides in order. Prefer to learn by doing? Jump to your wiki and start filling it out)

2. **Set up your wiki** (this is the most important part — everything else builds on what you document here)

3. **Feed the systems regularly** (weekly updates, new lessons, new tools)

4. **Watch your agent improve** (as systems get richer, agent gets smarter)

---

**Your AI agent is only as smart as the foundation you build for it.**

The 5 systems are the tools. You're the architect. Build them well, and everything else works.

---

## Support

If your agent seems to be making generic decisions:
- Likely cause: Wiki is incomplete or outdated
- Fix: Update `wiki/04-rules.md` and `wiki/01-businesses.md` with more detail

If your agent seems to miss context:
- Likely cause: Memory isn't being updated
- Fix: Review `MEMORY_ARCHITECTURE_SETUP.md` and update wiki monthly

If your agent suggests wrong tools:
- Likely cause: Tools Knowledge Base doesn't have what you need
- Fix: Tell agent "Add this tool to my tools database" with the problem it solves

If your agent repeats mistakes:
- Likely cause: Lessons aren't being captured
- Fix: Review `KNOWLEDGE_BASE_SETUP.md` and save lessons after important projects

---

**Version 2.0 — Updated 2026-06-04**  
Explains actual delivered systems (Memory, Rules, Frameworks, Tools DB, Knowledge Base) vs. claimed systems. All 5 setup docs created and included in preset package.
