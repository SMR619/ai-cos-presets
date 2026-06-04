# Research Module — Setup Checklist

## Before You Ask Me to Research Anything

### Step 1: API Keys (5 minutes)

#### Supadata API Key
1. Go to: https://supadata.ai
2. Sign up (free tier available)
3. Get your API key from dashboard
4. Store securely: Add to credentials.env as `SUPADATA_API_KEY`

**Purpose:** Pull transcripts from YouTube videos instantly

#### OpenAI API Key
1. Go to: https://platform.openai.com/account/api-keys
2. Create a new API key
3. Store securely: Add to credentials.env as `OPENAI_API_KEY`

**Cost:** ~$0.003 per video (Whisper API)  
**Purpose:** Transcribe audio from non-YouTube videos

---

### Step 2: File Structure (2 minutes)

Create these folders in your workspace:

```
/research/
├── /raw/              (raw transcripts go here)
└── /outputs/          (completed analysis files go here)
```

**Example:**
```bash
mkdir -p ~/research/raw
mkdir -p ~/research/outputs
```

---

### Step 3: Business Context (10 minutes)

Create a document: **"MY_BUSINESS_CONTEXT.md"** (1-2 pages)

Answer these questions:
- **What do you do?** (services, products, who you help)
- **What problems do you solve?** (specific pain points you address)
- **What's your revenue model?** (how you make money)
- **Who are your customers?** (target market)
- **Key metrics/goals?** (what success looks like for you)

**Why:** This helps me connect research directly to YOUR situation instead of generic insights.

**Example structure:**
```
## My Business Context

### What I Do
Level 19 Homes: Real estate investing using creative financing 
(subject-to, seller financing, hybrid deals)

### Problems I Solve
- Help people get capital for real estate deals
- Find deals using creative methods (not cash offers)

### Revenue Model
- Real estate wholesaling
- Coaching/community on funding strategies

### Customers
- Real estate investors looking for better financing methods
- People wanting to learn SubTo, Owners Club strategies

### Success Looks Like
- 5-10 deals per month
- $20K monthly net profit
```

---

### Step 4: Ready to Use! ✅

Once these are complete, you can ask me to research anything:

**Example requests:**
- "Research this video: [URL]"
- "Analyze this article for me: [URL]"
- "What does this podcast episode say about [topic]?"
- "Look into this tool and tell me if it's relevant: [link]"

---

## What Happens When You Ask Me to Research

1. **I confirm I have everything I need** (transcript access, business context)
2. **I pull the full source** (transcript from video/article)
3. **I analyze thoroughly** (frameworks, tools, insights specific to you)
4. **I organize findings** (structured output with action items)
5. **I save the file** (to /research/outputs/ for future reference)
6. **I explain what I found** (one-line summary + full analysis available)

**Timeline:** Most research takes 10-20 minutes from link to finished analysis.

---

## Troubleshooting

**Q: My Supadata key isn't working**
A: Check that it's in credentials.env with the right variable name (`SUPADATA_API_KEY`). Test with: `curl -H "x-api-key: YOUR_KEY" "https://api.supadata.ai/v1/youtube/transcript?url=..."`

**Q: I don't have an OpenAI API key yet**
A: You need one for non-YouTube videos. Go to platform.openai.com, create an account, generate an API key. Add $5-10 to your account for testing.

**Q: How do I know if the research is done?**
A: I'll tell you when it's done and give you a file path to read. Check `/research/outputs/` for the completed analysis.

---

**Questions?** Just ask. I'll help you get set up.

---

**Last Updated:** 2026-06-04  
**Status:** Active for new AI CoS agents
