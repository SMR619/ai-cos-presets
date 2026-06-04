# Memory Architecture — Setup & How It Works

Your AI agent remembers you and your business so it can make better decisions.

---

## What Memory Does

**Memory = Context**

Your agent's memory contains:
- What you've told it about your business
- What you care about
- What works for you
- What doesn't work
- Decisions you've made
- Lessons you've learned

Without memory: Agent has no context. Same question every time = same generic answer.  
With memory: Agent knows you, understands your business, gives personalized answers.

---

## How Your Agent Learns

**Tier 1: Immediate Context**  
Everything from this session. Agent reads your instructions, watches the conversation, understands what you're asking.

**Tier 2: Structured Knowledge**  
Your wiki (businesses, deals, people, rules), your instructions, your preferences. Agent references this for every decision.

**Tier 3: Long-term Learning**  
Session logs from previous conversations. Agent sees patterns in what you care about, what decisions you make, what works.

---

## Your Memory Files (You Update These)

### 1. Your Wiki (START HERE)
**Location:** `wiki/` folder

**What's in it:**
- `01-businesses.md` — Your business descriptions
- `02-deals.md` — Deal types and structures you use
- `03-people.md` — Key relationships and how to work with them
- `04-rules.md` — Your operating principles and decision rules
- `05-ies.md` — Company-specific details (if applicable)
- `06-instructions.md` — Procedures and how you do things

**When to update:** 
- When you have a new lesson learned
- When you onboard a new team member
- When your business model changes
- When you define a new rule or procedure

**Why it matters:** This is how your agent understands you and your business

---

### 2. Your Frameworks & Playbooks
**Location:** `frameworks/` folder

**What's in it:**
- Communication frameworks (storytelling, persuasion, etc.)
- Business frameworks (pricing, lead generation, etc.)
- Operations frameworks (scaling, team building, etc.)

**When to reference:** When you want your agent to communicate in a specific way, structure an idea using a specific framework, or apply a proven principle

---

### 3. Your Knowledge Base
**Location:** `knowledge/` folder

**What's in it:**
- `outputs/` — Analyzed findings from research, case studies, insights
- `lessons/` — Extracted lessons from books, videos, successful projects

**When to add to it:** After major research projects, after important lessons, after analyzing competitor moves or market data

---

## How Your Agent Uses Memory

### When you ask your agent to write an email:
Agent thinks: "Let me check [person's] communication preferences in the wiki... they prefer direct, no-fluff emails... okay, I'll write something short and to the point"

### When you ask your agent to evaluate a deal:
Agent thinks: "Let me check the deal rules in the wiki... Steve wants 20% value add minimum... and these deal structures are what Steve does... okay, does this deal fit?"

### When you ask your agent for advice:
Agent thinks: "Let me check the frameworks and lessons Steve has learned... this is similar to that situation Steve handled before... here's what worked then"

---

## Setup Checklist

- [ ] **Read your wiki README** — `wiki/README.md`
- [ ] **Start filling out your wiki** — Begin with businesses, rules, and key people
- [ ] **Review your frameworks folder** — Skim the frameworks to understand what's available
- [ ] **Explore your knowledge folder** — See what insights and lessons are already there
- [ ] **Add new lessons regularly** — After important experiences, add them to `lessons/`
- [ ] **Update wiki when things change** — New deal, new rule, new procedure? Update the wiki

---

## Memory Best Practices

✅ **DO:**
- Be specific in your wiki entries
- Update regularly (weekly if possible)
- Include real examples
- Document what you've learned
- Keep language conversational (write like you speak)
- Link to external resources and files

❌ **DON'T:**
- Leave the wiki empty — agent needs this to work well
- Keep secrets from the wiki — the more complete, the smarter the agent
- Write in corporate jargon — keep it real and direct
- Let old information pile up — update/delete outdated entries

---

## How Agent Technically Loads Your Memory

When you first activate your agent, it needs to load your memory files. Here's how it works:

**Initialization (First Time):**
1. Agent scans your `wiki/` folder
2. Agent reads: `01-businesses.md`, `04-rules.md`, `03-people.md` (priority files)
3. Agent loads your `frameworks/` folder index
4. Agent notes your `knowledge/lessons/` folder for reference
5. Agent caches this as its "baseline context"

**Every Time You Chat:**
1. Agent loads cached context (from previous sessions)
2. For each request, agent searches relevant memory:
   - Email about person X? → Check `03-people.md` for context
   - Evaluating deal? → Check `04-rules.md` + `02-deals.md` + `knowledge/lessons/`
   - Need communication approach? → Check `frameworks/communication-frameworks.md`
3. Agent includes relevant context in its reasoning
4. Agent gives response based on YOUR context

**You Update Memory:**
- Weekly: Update `wiki/04-rules.md`, `wiki/01-businesses.md` if things change
- After projects: Add lessons to `knowledge/lessons/`
- Anytime: Tell agent "Add this to my wiki" and I update in real-time

**Agent Keeps Up:**
- Agent checks for wiki updates each session
- If wiki changed since last session, agent reloads
- No manual refresh needed — it's automatic

---

## What Your Agent Does With Memory

**Before every decision, your agent:**
1. Loads your current wiki context (businesses, rules, people, procedures)
2. Checks your frameworks (how you think about problems)
3. Recalls relevant lessons (what you've learned before)
4. Makes a decision aligned with YOU, not generic best practices

---

## The Memory Cycle

```
You do something important
     ↓
You learn something from it
     ↓
You tell your agent (or write it in the wiki)
     ↓
Agent remembers it
     ↓
Next time a similar situation comes up, agent applies that learning
     ↓
Better decisions, faster execution
```

---

## Questions?

If your agent is making generic decisions or not understanding your context, it usually means:
- The wiki is incomplete
- Your rules aren't documented clearly
- New lessons haven't been captured

**Fix:** Tell your agent "Add this to my wiki" or "Update my rules" with the context. It learns.

---

**Memory is how generic AI becomes YOUR AI.**

The more complete your wiki, the smarter your agent. Invest in this and it pays back 10x.
