# Design Doc: Product for Product — Claude Code IRL Workshop

**Date:** 2026-02-20
**Status:** Approved
**Author:** Brainstorming session with Yonatan Kramer

---

## Overview

A 90-minute hands-on IRL Claude Code workshop for the "Product for Product" community. Audience: ~30 company PMs (employees, not freelancers). Beginner level. 1 assistant on-site.

**Core concept:** The GitHub repo IS the workshop. Participants clone it via Claude Code, then use its pre-made agents and skills to solve a real PM problem: Monday morning bug + feedback triage.

---

## What Participants Walk Away With

1. Claude Code installed and authenticated
2. A cloned GitHub repo containing their PM toolkit (CLAUDE.md, agents, skills, example files)
3. A prioritization doc produced by the bug-priority-analyzer agent
4. A stakeholder update written by the `/write-stakeholder-update` skill
5. Understanding of when to use agents vs skills

---

## Key Differences from Meetup 4

| | Meetup 4 | PFP Workshop |
|--|---------|-------------|
| Audience | Freelance PMs | Company PMs (employees) |
| Duration | 3 hours | 90 minutes |
| Participants | ~50 | ~30 |
| Files source | Created from scratch | Cloned from GitHub repo |
| CLAUDE.md | Built by participant | Pre-made (company PM context) |
| Final output | PRD + mockup | Bug triage report + stakeholder update |
| Git | Not covered | Conceptual + practical clone via Claude Code |
| Agents vs Skills | Not differentiated | Explicitly taught |

---

## Workshop Architecture (Three Acts)

### Act 1: Setup (00:00–00:25)
- Install Claude Code + authenticate (15 min)
- Git/GitHub conceptual explanation via slides (3 min)
- Claude Code runs `git clone` — the teaching moment: "I didn't type a single git command" (7 min)

**Pre-requirement for participants:** Git installed before arriving

### Act 2: Explore (00:25–00:50)
- Tour the CLAUDE.md: what it is, company PM framing, how to adapt it (10 min)
- Tour agents vs skills: the core conceptual slide, walk the folder (15 min)
  - Agents: autonomous, open-ended tasks, Claude decides how
  - Skills: slash commands, known output format, participant triggers manually
  - Table comparison on slide
  - Walk `.claude/agents/` and `.claude/skills/` in terminal

### Act 3: Build (00:50–01:30)
- Hands-on Step 1: Run `bug-priority-analyzer` agent on `example-files/bug-reports.txt` (15 min)
- Hands-on Step 2: Run `/write-stakeholder-update` skill on the output (10 min)
- Share: 2 people show output on projector (5 min)
- Wrap up + next steps (5 min)

---

## GitHub Repository Structure

**Repo name:** `product-for-product-workshop` (public)

```
product-for-product-workshop/
├── README.md                          # Hebrew guide — open this in Claude Code first
├── CLAUDE.md                          # Pre-filled: company PM, B2B SaaS "Telos"
├── .claude/
│   ├── agents/
│   │   ├── bug-priority-analyzer.md   # ⭐ Main workshop agent (to be created separately)
│   │   ├── user-feedback-analyzer.md  # Adapted from Meetup 4
│   │   ├── sprint-backlog-prioritizer.md
│   │   └── meeting-summary.md         # Reused from Meetup 4
│   └── skills/
│       ├── prioritize.md              # Reused from Meetup 4
│       ├── write-stakeholder-update.md  # NEW
│       └── create-user-stories.md     # Reused from Meetup 4
├── example-files/
│   ├── bug-reports.txt                # 50 bugs, Telos B2B SaaS (Hebrew)
│   ├── user-feedback.txt              # 30 feedback items (Hebrew)
│   └── sprint-backlog.txt             # 20 sprint tasks (Hebrew)
└── workshop-commands.md               # Copy-paste Hebrew prompts for each step
```

**Fictional product:** "Telos" — a B2B SaaS project management tool. Generic enough that all company PMs can relate.

**Note on agents:** `bug-priority-analyzer.md` will be created separately using the agent creator and added manually to the repo.

---

## Slide Deck (9 slides)

**Format:** Reveal.js HTML, Hebrew RTL, black theme — same base as `Meetup-4-IRL-Workshop/meetup-4-presentation.html`

| # | Slide | Key visual |
|---|-------|-----------|
| 1 | Title + "בעוד 90 דקות יהיה לך..." | Final output screenshot |
| 2 | Installation commands | Code block |
| 3 | מה זה Git ו-GitHub? | "המדף המשותף" visual |
| 4 | Clone via Claude Code | Terminal screenshot / command |
| 5 | מה זה CLAUDE.md? | Onboarding doc analogy |
| 6 | Agents vs Skills — הטבלה | Comparison table |
| 7 | Agents: מתי ולמה | Examples |
| 8 | תרחיש יום שני בבוקר | The challenge setup |
| 9 | Wrap up + next steps | Repo link + community |

---

## Content Reused from Meetup 4

| File | Source | Change |
|------|--------|--------|
| `user-feedback-analyzer.md` | Meetup 4 agents | Minor: adapt to company PM context |
| `meeting-summary.md` | Meetup 4 skills | None — reuse as-is |
| `prioritize.md` | Meetup 4 skills | None — reuse as-is |
| `create-user-stories.md` | Meetup 4 skills | None — reuse as-is |
| Reveal.js HTML structure | meetup-4-presentation.html | Replace content, keep CSS/theme |

---

## New Files to Create

| File | Notes |
|------|-------|
| `CLAUDE.md` | Company PM template, pre-filled with Telos SaaS context |
| `README.md` | Hebrew guide, opened in Claude Code as first action |
| `bug-reports.txt` | 50 realistic bugs, Telos, Hebrew |
| `user-feedback.txt` | 30 feedback items, Telos, Hebrew |
| `sprint-backlog.txt` | 20 sprint tasks, Telos, Hebrew |
| `workshop-commands.md` | Hebrew prompts for each step |
| `write-stakeholder-update.md` | New skill |
| `sprint-backlog-prioritizer.md` | New agent |
| `pfp-workshop-presentation.html` | 9-slide deck based on Meetup 4 |
| `WORKSHOP-PLAN.md` | Speaker agenda with full narration + timing |

---

## Agenda Timing Detail

```
00:00  Welcome (assumed from event host)
00:00  [Yonatan] Installation starts — Claude Code install + auth
00:15  [Slides] Git/GitHub — 3 min conceptual
00:18  [Terminal] Claude Code runs git clone
00:25  [Slides + MD] CLAUDE.md tour
00:35  [Slides + Terminal] Agents vs Skills tour
00:50  [Terminal] Hands-on Step 1: bug-priority-analyzer
01:05  [Terminal] Hands-on Step 2: /write-stakeholder-update
01:15  [Projector] 2 participants share output
01:20  [Slides] Wrap up + next steps
01:25  Buffer / Q&A
01:30  End
```

---

## Key Teaching Moments

1. **The clone moment:** Claude Code runs `git clone` — "notice I didn't type a git command"
2. **The triage moment:** Agent processes 50 bugs in ~2 min — "this is your Monday morning, solved"
3. **The skill moment:** `/write-stakeholder-update` turns raw output into a Slack-ready message
4. **The debrief:** "You now have priorities + a message ready to paste. That's your day back."

---

## ROI Message

> "This agent just did what would take you 2 hours on a Monday morning. In 3 minutes. Every Monday."

---

*Approved: 2026-02-20*
