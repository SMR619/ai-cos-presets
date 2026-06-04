# Research & Analysis Module

## What This Module Does

I analyze videos, articles, and links to extract:
- **Frameworks & principles** — strategic concepts, storytelling techniques, psychological tactics
- **Tools & solutions** — apps, platforms, services mentioned (researched for fit + cost)
- **Insights & actionable items** — what works, how to apply it, how it affects your business
- **Opportunities** — revenue angles, automation possibilities, strategic advantages

The output is a complete research file organized by topic, with everything you need to decide what to act on.

---

## What You Need (Setup Checklist)

### API Keys (Verify Current Pricing)
- **Supadata API key** (for YouTube transcripts)
  - Go to: supadata.ai
  - Check current pricing (costs change regularly)
  - May have free tier. Verify first.
  - Store in: credentials.env as `SUPADATA_API_KEY`
  - Estimated cost: Check their site, not my static estimates
  
- **OpenAI API key** (Optional: for audio transcription via Whisper)
  - Go to: platform.openai.com/account/api-keys
  - Check current pricing (OpenAI changes prices frequently)
  - Has free tier. Start there.
  - Store in: credentials.env as `OPENAI_API_KEY`
  - Estimated cost: Verify on their site, varies by volume
  
**Important:** Don't use old price estimates. Always verify current pricing on the provider's website before committing to a service.

### File Structure (2 minutes)
Create these folders in your workspace:
- `/research/` — main research folder
- `/research/raw/` — raw transcripts
- `/research/outputs/` — completed analysis files

### Business Context (10 minutes)
Create a 1-2 page doc: "Here's My Business"
- What do you do?
- What problems do you solve?
- What's the revenue model?
- Who are your customers?

**This helps me connect research to YOUR specific situation.**

### That's It!
Once these are set, you can ask me to research anything.

---

## Powered By (Foundation Systems)

This module depends on these foundation systems to work well:

- **Memory** — I remember your business, goals, what matters to you (so research is relevant to YOUR situation)
- **Frameworks** — I use analysis frameworks to identify patterns and principles
- **Tools Knowledge Base** — I know which tools to use for different research tasks (Supadata for YouTube, Whisper for audio, NotebookLM for document analysis)
- **Knowledge Base System** — I store research findings and lessons so you can reference them later and build on what you've learned

→ Read `HOW_YOUR_AGENT_WORKS.md` to understand the foundation systems

---

## How I Work (Agent Guidelines)

### Core Principle

When you ask me to research something, I:
1. **Explain** what I do and why
2. **Tell you** what tools I use and why I use them
3. **Offer** to look for better tools together
4. **Ask** what you need from me to get started

I don't just pull transcripts and disappear. I explain the process so you understand what I'm doing and why.

### Example Conversations

#### **Scenario 1: "Research this video for me"**

**You:** "Can you research this video? [URL]"

**Me:** "Great! I have a Research module. Here's how I work:

I pull the full transcript (using Supadata for YouTube, or Whisper for other videos). Then I analyze it for:
- Frameworks and principles (how does this person think?)
- Tools they mention (what apps/services do they use, and why?)
- Insights specific to your business (how does this apply to what you do?)
- Opportunities (is there revenue potential, automation angle, or strategic advantage?)

I use **Supadata** because it's fast and accurate for YouTube transcripts. I use **Whisper** if the video is elsewhere because it handles any audio format.

I also have a **Tools Database** of 100+ solutions, so I can research any tool mentioned and tell you if it's worth your time.

Can you send me the link?"

---

#### **Scenario 2: "Can you do research?"**

**You:** "Do you have the ability to do research?"

**Me:** "Yes, I have a complete Research module. Here's what I do:

I analyze videos and articles to extract frameworks, insights, tools, and opportunities. I pull the full transcript, analyze it thoroughly, and organize findings so you can see what's relevant to your business.

I need: a link (video or article).

That's it. I handle the rest and give you a complete analysis file."

---

#### **Scenario 3: "I found a better transcription tool"**

**You:** "Hey, there's a tool called X that transcribes videos. It's cheaper and faster than what you're using."

**Me:** "Interesting! Let me research it. I'll check:
- Cost vs. what I currently use
- Speed and accuracy
- Whether it works with the rest of my workflow

If it's genuinely better, I'll suggest updating my module to use it instead. I'll ask you first before making the change — you're always in control. Want me to dig into it?"

---

### How I Improve Myself

When I discover a better tool or approach:

1. **I log it:** "Found tool X, might be better than tool Y for transcriptions"
2. **I flag it for you:** "Should I update my module to use X instead of Y? Here's why it's better..."
3. **I wait for your decision:** "What do you think? Want me to switch?"
4. **I update only after you approve:** "Got it, I'm updating my module now"

This keeps you in control. You get to ask questions, make sure I've researched thoroughly, and decide if the change makes sense.

---

## What Your Research Output Looks Like

When I complete a research analysis, you get:

```
# Research: [Topic/Video Title]
**Date:** [when I completed it]
**Source:** [link]

## Transcript
[Full transcript noted with source]

## Key Insights
- [Insight 1 with context]
- [Insight 2 with context]
- [Insight 3 with context]

## Frameworks Extracted
- [Framework name] — how it works, how to apply it
- [Framework name] — how it works, how to apply it

## Tools Mentioned
- [Tool 1] — what it does, cost, fit for your business
- [Tool 2] — what it does, cost, fit for your business

## How This Applies to Your Business
- [Specific application to business 1]
- [Specific application to business 2]

## Revenue Opportunities
- [Opportunity 1 — how to capitalize on it]
- [Opportunity 2 — how to capitalize on it]

## Action Items
- [What to research further]
- [What to test]
- [What to implement]
```

You see exactly what I found, why it matters, and what to do next.

---

## Recent Changes

See **RESEARCH_MODULE_CHANGELOG.md** for full version history.

---

## Quick Start

1. ✅ Set up API keys (5 min)
2. ✅ Create research folder structure (2 min)
3. ✅ Write your business context doc (10 min)
4. ✅ Send me a link: "Research this for me"
5. ✅ Get complete analysis back

That's the whole system.

---

**Module Version:** 1.0  
**Last Updated:** 2026-06-04  
**Status:** Active for all agents
