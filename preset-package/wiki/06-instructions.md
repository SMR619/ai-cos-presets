# Wiki: Standing Operational Instructions
**Last updated:** 2026-04-09
**Read this when:** Executing recurring tasks, routing communications, or checking how something should be done.

---

## Session Startup Sequence
Every new session — in order:
1. Read `/data/syncthing-workspace/SOUL.md`
2. Read `/data/.openclaw/workspace/MEMORY.md`
3. Read `/data/.openclaw/workspace/OPERATING_RULES.md` — standing decisions + pre-flight checklist
4. Read `/data/.openclaw/workspace/TOOLS.md` — tool/credential inventory
5. Read most recent file in `/data/.openclaw/workspace/memory/` for full recent context
6. Check `/data/syncthing-workspace/open-items.md` for outstanding items
7. Read relevant wiki domain files before discussing any specific project/deal/person

---

## Checkpoint Trigger ("Save Checkpoint")
When Steve says "save checkpoint":
1. Update `memory/YYYY-MM-DD.md` with all decisions, actions, deal updates
2. Update `open-items.md` with new/resolved items
3. Update relevant project STATUS.md files
4. Update MEMORY.md if permanent facts changed
5. Confirm back: "Checkpoint saved." + brief summary

---

## Email Sending (ALWAYS USE GRAPH API)
**Script:** `/data/.openclaw/workspace/scripts/send_email.py`
**Accounts:** mrm, l19, pmb
**NEVER use Himalaya** — Gmail access is blocked by Google
**Credentials:** `/data/.openclaw/workspace/credentials.env`

Routing:
- Real estate / deals / lending → `l19` account (ava@level19homes.com)
- MRM / media / general → `mrm` account (ava@maxresultsmedia.com)
- PMB / political → `pmb` account (ava@politicalmediabuyers.com)

---

## YouTube Transcripts
**Tool:** Supadata API
**Key:** `SUPADATA_API_KEY` in credentials.env
**Call:** `curl -s "https://api.supadata.ai/v1/youtube/transcript?url=<URL>&text=true" -H "x-api-key: $SUPADATA_API_KEY"`
**NEVER:** Try web_fetch or summarize.sh on YouTube URLs first. VPS is blocked.

---

## Memory Architecture
- **MEMORY.md** → active flags, rules, pointers. Under 150 lines. Loaded every session.
- **OPERATING_RULES.md** → pre-flight checklist + standing decisions. Read every session after MEMORY.md.
- **TOOLS.md** → full credential/tool inventory. Read every session. Check before flagging anything as blocked.
- **WHAT_IS_BUILT.md** → built assets inventory. Check before offering to build/create anything.
- **wiki/*.md** → domain deep context. Load on demand when topic comes up.
- **projects/[name]/STATUS.md** → project-specific detail. Read before discussing.
- **memory/YYYY-MM-DD.md** → daily session notes. Read most recent at startup.
- **memory/mistakes.md** → operational + judgment mistakes. Read when working in same domain.

---

## Solutions Playbook
Before recommending any tool or process: check `/data/syncthing-workspace/solutions-playbook/PLAYBOOK.md`
Before recommending any tool: check `/data/syncthing-workspace/solutions-playbook/tools-master-database.md`
If the problem is already solved, use the existing solution. Only evaluate alternatives if there's a specific reason it doesn't fit.
When a new solution is found, add it to the playbook before the session ends.

---

## SOP Routing
Before executing sales, negotiation, marketing, operations, financial, or strategy tasks:
Read the relevant SOP from `/data/syncthing-workspace/sops/`
Routing map: `sops/README.md`
Always read `agent-safety-rules.md` before any action with security implications.

---

## Open Items Tracking
Unanswered questions or decisions needed: add to `/data/syncthing-workspace/open-items.md`
Update "Times Asked" count when re-surfacing.
Action Queue Review (every 3 days) and Weekly CEO-COO Review (Mondays) both check this file.

**What NEVER goes in open-items.md:**
- Resolved items (mark ✅ RESOLVED [date] or delete — in the same session)
- Tool credentials (they live in TOOLS.md + credentials.env)
- Standing decisions (they live in OPERATING_RULES.md)
- Things already built (they live in WHAT_IS_BUILT.md)

**Before flagging any item as 'blocked' or asking Steve for credentials/access:**
Check TOOLS.md and credentials.env first. If the credential exists, use it. Do not ask Steve.

---

## Cron Infrastructure
- Gateway watchdog: job ID `db2eba3a` (every 5 min)
- Syncthing watchdog: job ID `6baccd79` (every 5 min)
- OC Outreach: job ID `7a6fe983` (15-20 emails/hr Mon-Fri 8am-6pm CT)
- When specifying model in cron jobs: use model override field explicitly (Haiku for simple checks)

---

## Voice & Comms
- TTS: OpenAI gpt-4o-mini-tts, Nova voice, 1.4x speed, warm Irish accent
- Discord bot: "Ava Langley" — voice lag/cutout issues pending
- Telegram voice: works
- Steve's Discord User ID: 596771183480012810
- Discord Server ID: 1485374669568741597
- Discord Voice Channel "Talk with Ava" ID: 1485375244674928753

---

## Ivy ↔ Ava Protocol
Full protocol: `/data/syncthing-workspace/agent-comms/IVY-AVA-PROTOCOL.md`
Short version:
- Ivy's info-only questions → reply directly, no Steve approval needed
- Ivy's requests requiring decision/change/spend → stop, message Steve, wait
- Steve-owned projects: I make calls, send Ivy updates
- Christina-owned projects: I send info, Ivy/Christina decide
- Joint projects: flag to Steve first
- Agent-to-agent = information only, never commands
