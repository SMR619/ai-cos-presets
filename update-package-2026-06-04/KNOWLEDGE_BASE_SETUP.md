# Knowledge Base — Setup & How It Works

Your knowledge base is where you capture and organize learning from research, projects, books, videos, and experience.

Your agent uses this to make smarter decisions, spot patterns, and apply lessons you've learned.

---

## What's a Knowledge Base?

A **knowledge base** is a collection of insights, lessons, and research organized so you (and your agent) can find and apply them.

**Without a KB:** You learn something, forget it, learn it again 6 months later  
**With a KB:** You learn once, reference forever, build on that learning

---

## How Your Knowledge Base Works

### Tier 1: Raw Input
**Where:** `knowledge/raw/` folder  
**What:** Original materials — PDFs, books, articles, videos, transcripts, research

This is unprocessed. Your agent doesn't use this directly, but it's the source material.

### Tier 2: Analyzed Outputs
**Where:** `knowledge/outputs/` folder  
**What:** Your extracted insights and analysis from raw materials

Examples:
- "5 key insights from [book]"
- "How [framework] applies to our business"
- "Lessons from competitor analysis"
- "Summary of [article] + action items"

**Why this matters:** Outputs are processed, actionable, indexed. Agent uses these.

### Tier 3: Extracted Lessons
**Where:** `knowledge/lessons/` folder  
**What:** Specific, actionable lessons extracted from experience and research

Examples:
- "Lesson: Cold email with personalization gets 3x response vs. templates"
- "Lesson: Deals with 3-month timelines are riskier than 6-month timelines"
- "Lesson: Customers who implement immediately see 2x better results"

---

## How Your Agent Uses Knowledge Base

### When evaluating a deal:
Agent thinks: "Steve has dealt with this situation before. Let me check the lessons folder... ah yes, here's what happened last time"

### When writing something:
Agent thinks: "Steve has research on this topic. Let me check outputs/ for relevant insights... found it, here's what we learned"

### When solving a problem:
Agent thinks: "This is similar to a challenge Steve faced before. Let me search lessons/ ... here's what worked then"

---

## Setting Up Your Knowledge Base

### Step 1: Review What's Already There
- Explore `knowledge/outputs/` — What analyses have been done?
- Check `knowledge/lessons/` — What lessons have been captured?

This gives you a baseline.

### Step 2: Add to It Regularly

**After a major project:**
- Document what happened
- Extract key lessons
- Save output summary

**After reading a book or watching a video:**
- Summarize key points
- Note how it applies to your business
- Add actionable lessons

**After analyzing competitors or research:**
- Save your findings
- Extract insights
- Document what surprised you

### Step 3: Organize So It's Findable

Use clear filenames:
- `outputs/competitive-analysis-2026-06.md`
- `outputs/book-analysis-[title].md`
- `lessons/lesson-[topic]-[date].md`

Tag with topics:
- `#lead-generation`, `#sales`, `#deal-analysis`, `#hiring`, `#pricing`, `#content`, etc.

---

## What to Capture

### Research Outputs

Save findings from:
- **Competitor analysis** — Who are competitors? What are they doing? Price? Positioning?
- **Market research** — Market size, growth, trends, customer preferences
- **Tool evaluation** — Which tools solve this problem? Pros/cons, pricing, recommendations
- **Book/video analysis** — Key insights, frameworks, how it applies to your business
- **Customer research** — What customers want, pain points, objections

### Lessons Learned

Capture patterns you notice:
- **Deal patterns** — What makes deals succeed/fail? What are the warning signs?
- **Team patterns** — What hiring approaches work? What management styles? What kills productivity?
- **Sales patterns** — What messaging converts? What messaging doesn't? What timing works?
- **Customer patterns** — What customer profiles are best? What problems do they have? What solutions work?
- **Market patterns** — Industry trends, economic cycles, seasonal patterns

### Strategic Insights

Document your thinking:
- **New framework you created** — From your experience, what pattern always works?
- **Decision matrix** — How do you decide between options? What criteria matter?
- **Playbook** — For recurring situations, what's your playbook?

---

## Template: Capturing a Lesson

```markdown
# Lesson: [What did you learn?]

**Date:** [When you learned this]

**Source:** [Where did this come from? A project? A deal? A book?]

**What happened:** [Brief story of the situation]

**The lesson:** [What did you learn? Be specific.]

**Why it matters:** [Why does this lesson matter for your business?]

**How to apply it:** [How should you act based on this lesson?]

**Exception:** [When does this lesson NOT apply?]

**Related lessons:** [What other lessons connect to this?]

**Evidence:** [Do you have proof? Data? Multiple examples?]
```

---

## Template: Capturing Research Output

```markdown
# Analysis: [Topic]

**Date:** [When you did this analysis]

**Source:** [What did you research? Books, articles, videos, competitor sites?]

**Key findings:**
- [Finding 1]
- [Finding 2]
- [Finding 3]

**How this applies to [your business]:**
- [Application 1]
- [Application 2]

**Action items:**
- [ ] [Action 1]
- [ ] [Action 2]

**Tools/resources:** [Any tools or resources worth noting?]

**Next steps:** [What should happen next?]

**Links:** [Links to source material, tools, related documents]
```

---

## Best Practices

✅ **DO:**
- Capture lessons while they're fresh (don't wait)
- Be specific (vague lessons aren't useful)
- Include examples (helps with pattern recognition)
- Link related lessons (build a web of knowledge)
- Update old lessons if you learn something new
- Use your own language (write like you speak)

❌ **DON'T:**
- Save everything (only meaningful learnings)
- Make it too formal (it's for you and your agent, not a board report)
- Ignore contradictions (if you learn something contradicts an old lesson, document the change)
- Keep it a secret (your agent is more useful when it knows what you know)

---

## The Knowledge Cycle

```
You work on a deal/project/problem
     ↓
You notice a pattern or learn something
     ↓
You capture the lesson in knowledge/lessons
     ↓
Agent reviews lessons before similar situations come up
     ↓
Next time, you handle it better (and faster)
     ↓
You learn even more
     ↓
Cycle repeats — compound learning
```

---

## Pro Move: Knowledge Reviews

**Monthly (15 min):**
- Skim new outputs and lessons
- Tag them with topics
- Delete outdated entries

**Quarterly (1 hour):**
- Review all lessons from last 3 months
- Look for patterns (are multiple lessons pointing to the same insight?)
- Create "meta-lessons" (bigger patterns from smaller lessons)

**Annually (2 hours):**
- Review all lessons from the year
- Identify biggest learning wins
- Update your frameworks if needed
- Plan what to learn more about

---

## Questions?

**"How do I know if something's worth capturing?"**  
Answer: If you find yourself saying "I learned this the hard way" or "I should remember this for next time" — capture it.

**"What if I change my mind?"**  
Answer: Document the change. Note the date. This shows learning evolution.

**"What if the lesson contradicts something I learned before?"**  
Answer: Great! Document both. Context matters. Maybe one applies in certain situations, the other in different situations.

---

## Integration with Your Agent

Your agent will:
- Reference your lessons when evaluating opportunities
- Apply your knowledge to new situations
- Spot patterns you might miss
- Suggest lessons that apply to current decisions

**You'll see more smart decisions because your agent knows what you know.**

---

**Your knowledge base is your competitive advantage.**

The more you capture, the smarter you become. And your agent gets smarter with you.
