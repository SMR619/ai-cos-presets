# Solutions Playbook — Review Protocol

## When to Add a New Entry
Any time Steve and Ava evaluate a problem and land on a solution — add the entry before the session ends, while the reasoning is fresh. Don't wait. Context decays.

Template to copy:
```
### [Problem Title]
**Problem:**
**Solution:**
**Cost:**
**Setup complexity:** Low / Medium / High
**Status:** Live ✅ / Planned 🔄 / Evaluating 🔍 / Deprecated ❌
**Why this over alternatives:**
**Alternatives considered:**
**Ava integration:**
**Notes:**
```

---

## Monthly Review (trigger: first Monday of each month)
1. Check `/data/syncthing-workspace/rich-queue/` for any tool mentions that intersect with existing playbook categories
2. Flag anything newer, cheaper, or meaningfully better to Steve with a quick summary: "Rich found X — it does the same thing as Y we use, but costs $Z less / has this capability we don't have. Worth a look?"
3. Add 🔴 REVIEW NEEDED tag to any flagged entry in PLAYBOOK.md
4. Surface all flagged entries in the next Weekly CEO-COO Review

---

## Quarterly Deep Review (trigger: first Monday of each quarter)
1. Re-check pricing on every "Cost" field in PLAYBOOK.md
2. Any pricing that has changed >20% — flag with 🔴 REVIEW NEEDED and note the new price
3. Check "Status: Planned 🔄" entries — if still not started after 2+ quarters, either start or mark deprecated
4. Verify all "Ava integration" fields are still accurate (APIs don't always stay stable)

---

## On New Project Start
Before recommending any tool or process for a new project:
1. Check PLAYBOOK.md — if the problem is already solved, use the existing solution
2. Only evaluate alternatives if there's a specific reason the existing solution doesn't fit (cost, capability gap, different context)
3. Document the reason if deviating from the playbook

---

## Stale Entry Protocol
- Tag with `🔴 REVIEW NEEDED` inline in PLAYBOOK.md
- Note what specifically needs checking (pricing? still active? better alternative found?)
- Surface at next Weekly CEO-COO Review (Monday 9am ET)
- Do not delete entries — mark as `Status: Deprecated ❌` with a note on what replaced it and why

---

## Rich Queue Integration
When Rich is active and processing YouTube/content research:
- Watch his output for tool mentions in these categories: CRM, email, analytics, automation, AI models, real estate data, e-sign, payments
- Cross-reference against PLAYBOOK.md — if a tool he finds overlaps with a category we already have a solution for, note it
- The goal isn't to switch tools constantly — it's to make sure we're not missing something materially better
