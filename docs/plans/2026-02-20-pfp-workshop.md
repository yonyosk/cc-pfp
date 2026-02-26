# PFP Workshop Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Create all files for the "Product for Product" Claude Code IRL Workshop — a 90-minute hands-on session for ~30 company PMs.

**Architecture:** A public GitHub repo serves as the workshop toolkit. Participants clone it via Claude Code, explore pre-made CLAUDE.md + agents + skills, then run a bug triage + stakeholder update workflow on example files. A Reveal.js presentation (based on Meetup 4) guides the room.

**Tech Stack:** Markdown, Reveal.js HTML (copied from Meetup 4 as base), plain text example files. No build step. No dependencies.

**Design doc:** `docs/plans/2026-02-20-pfp-workshop-design.md`

**Source to reuse:** `C:\Users\yonyo\Documents\My Projects\YK Notes\Claude-Code-Meetups\Meetup-4-IRL-Workshop\`

---

## Folder Structure

All files live under:
```
C:\Users\yonyo\Documents\My Projects\YK Notes\Claude-Code-Meetups\PFP-Workshop\
```

Final structure when complete:
```
PFP-Workshop/
├── docs/plans/                        # (already exists — design docs)
├── README.md
├── CLAUDE.md
├── WORKSHOP-PLAN.md
├── pfp-workshop-presentation.html
├── workshop-commands.md
├── .claude/
│   ├── agents/
│   │   ├── bug-priority-analyzer.md   # Created manually by Yonatan (skip this task)
│   │   ├── user-feedback-analyzer.md
│   │   ├── sprint-backlog-prioritizer.md
│   │   └── meeting-summary.md
│   └── skills/
│       ├── prioritize.md
│       ├── write-stakeholder-update.md
│       └── create-user-stories.md
└── example-files/
    ├── bug-reports.txt
    ├── user-feedback.txt
    └── sprint-backlog.txt
```

---

## Task 1: Create README.md

**Files:**
- Create: `PFP-Workshop/README.md`

**Step 1: Write the file**

```markdown
# סדנת Claude Code — Product for Product

ברוכים הבאים! זהו ה-toolkit שלכם לסדנה.

## מה יש כאן?

- **CLAUDE.md** — קובץ ה-context לפרויקט (Claude קורא אותו אוטומטית)
- **.claude/agents/** — סוכנים מוכנים לעבודה אוטונומית
- **.claude/skills/** — פקודות מהירות לתוצרים קבועים
- **example-files/** — קבצי דוגמה לתרגול

## מוצר הדוגמה: Telos

כל קבצי הדוגמה מתייחסים ל-**Telos** — פלטפורמת ניהול פרויקטים B2B SaaS.
השתמשו בה כבסיס לתרגול, ואחר כך החליפו לפרויקט האמיתי שלכם.

## איך להתחיל?

1. פתחו את Claude Code בתיקייה הזו:
   ```
   claude
   ```
2. שאלו את Claude: `מה יש בתיקייה הזו?`
3. עקבו אחרי הסדנה 🚀

## אחרי הסדנה

- החליפו את ה-CLAUDE.md לפרויקט האמיתי שלכם
- השתמשו בסוכנים וב-skills על הקבצים שלכם
- שאלות? קהילת Product for Product תמיד פה
```

**Step 2: Verify**
Open the file in your MD reader. Confirm Hebrew renders correctly, structure is clear.

---

## Task 2: Create CLAUDE.md

**Files:**
- Create: `PFP-Workshop/CLAUDE.md`

**Step 1: Write the file**

```markdown
# Telos — Product Context

## Product Overview
**Product:** Telos
**Type:** B2B SaaS — Project Management Platform
**Stage:** Growth (Series B)
**Team size:** 45 employees (12 in product & engineering)

## What We Build
Telos helps mid-size companies (50–500 employees) manage cross-team projects.
Core features: task management, sprint planning, team dashboards, integrations (Slack, Jira, GitHub).

## Our Users
### Primary: Project Managers (our champion)
- Pain: too many tools, too little visibility across teams
- Goal: one place to see everything, report to leadership
- Technical level: medium (uses Jira, Notion, Slack daily)

### Secondary: Team Members
- Pain: unclear priorities, constant context switching
- Goal: know what to work on, in what order

## Business Goals (This Quarter)
1. Reduce churn: target 4% monthly → 2.5%
2. Increase activation: 30% of signups reach "first project created" within 48h (currently 18%)
3. Enterprise readiness: SSO + audit logs for deals >$50k/year

## My Role
Product Manager — Growth & Retention squad
- Own: onboarding flow, notifications, integrations
- Deliverables: PRDs, user stories, prioritization docs, stakeholder updates
- Stakeholders: VP Product (Noa), CTO (Avi), Customer Success lead (Dana)

## Tech Stack (for context)
- Frontend: React + TypeScript
- Backend: Node.js + PostgreSQL
- Infrastructure: AWS
- Integrations: Slack, Jira, GitHub, Zapier

## Working Preferences for Claude
- Language: Hebrew preferred, English for technical terms
- Always ask clarifying questions before starting a document
- Use bullet points, headers, tables — easy to scan
- Include "Open Questions" section in all docs
- When prioritizing: use RICE or Impact/Effort, show your reasoning
- Stakeholder updates: short, clear, one action item at the end

## Sprint Cadence
- 2-week sprints
- Planning: Sunday morning
- Retro + demo: Thursday end of sprint
- Current sprint: Sprint 47

## Key Files in This Project
- `example-files/bug-reports.txt` — current open bugs (imported from Jira)
- `example-files/user-feedback.txt` — this week's user feedback
- `example-files/sprint-backlog.txt` — Sprint 48 candidate items

---
*Last updated: 2026-02-20*
*Template based on PFP Workshop — replace with your real project details*
```

**Step 2: Verify**
Confirm the company PM context is clear. Confirm it's distinct from the freelancer template in Meetup 4.

---

## Task 3: Create example-files/bug-reports.txt

**Files:**
- Create: `PFP-Workshop/example-files/bug-reports.txt`

**Step 1: Write the file**

This file needs 50 realistic B2B SaaS bugs for Telos. Write in Hebrew. Mix of severities (Critical/High/Medium/Low) and areas (performance, UI, integrations, notifications, auth). Format each bug consistently:

```
---
מזהה: BUG-[number]
כותרת: [title]
דיווח על ידי: [name or role]
תאריך: [date in 2026]
חומרה: [קריטי / גבוה / בינוני / נמוך]
תחום: [ביצועים / ממשק משתמש / אינטגרציות / התראות / אימות / אחר]
תיאור: [2-3 sentences describing the bug]
השפעה: [who is affected and how many]
---
```

Write all 50 bugs. Examples to use as pattern:

```
---
מזהה: BUG-001
כותרת: לוח הבקרה נטען לאט כשיש יותר מ-50 משימות פתוחות
דיווח על ידי: Customer Success — דנה כהן
תאריך: 2026-02-10
חומרה: גבוה
תחום: ביצועים
תיאור: כשמשתמש נכנס ללוח הבקרה עם יותר מ-50 משימות פתוחות, הטעינה לוקחת 8-12 שניות. בלקוחות גדולים (100+ משימות) הדף קופא לפרק זמן. הבעיה מתרחשת בכל הדפדפנים.
השפעה: 23% מהחשבונות (לקוחות enterprise) — 340 משתמשים פעילים.
---

---
מזהה: BUG-002
כותרת: אינטגרציית Slack לא שולחת התראות על משימות שעברו את הדד-ליין
דיווח על ידי: לקוח — Amir, WeWork IL
תאריך: 2026-02-12
חומרה: גבוה
תחום: אינטגרציות
תיאור: ההתראות לסלאק אמורות לצאת כשמשימה עוברת את תאריך הסיום ללא השלמה. בפועל ההתראה לא יוצאת. הגדרת ה-webhook תקינה. הבעיה החלה לאחר עדכון v2.4.1.
השפעה: כל המשתמשים עם אינטגרציית Slack פעילה — 1,200 משתמשים.
---

---
מזהה: BUG-003
כותרת: כפתור "צור משימה חדשה" לא מגיב בנייד (iOS Safari)
דיווח על ידי: QA — יוסי לוי
תאריך: 2026-02-14
חומרה: קריטי
תחום: ממשק משתמש
תיאור: בגרסת iOS Safari (16+), לחיצה על כפתור "צור משימה חדשה" לא פותחת את הטופס. הכפתור מקבל focus אבל לא מתרחש שום אירוע. בכרום לנייד הכל עובד תקין.
השפעה: כל משתמשי iOS Safari — כ-30% מהמשתמשים הניידים.
---

---
מזהה: BUG-004
כותרת: ייצוא ל-CSV לא כולל שדות מותאמים אישית
דיווח על ידי: לקוח — רחל, Ness Technologies
תאריך: 2026-02-11
חומרה: בינוני
תחום: ממשק משתמש
תיאור: כשמשתמש מייצא רשימת משימות ל-CSV, שדות מותאמים אישית (custom fields) לא מופיעים בקובץ. רק השדות הסטנדרטיים כלולים. הבעיה קיימת מגרסה 2.3.
השפעה: לקוחות עם custom fields — כ-180 חשבונות.
---

---
מזהה: BUG-005
כותרת: איפוס סיסמה — המייל לא מגיע ב-Gmail
דיווח על ידי: Support — מיכל אברהם
תאריך: 2026-02-15
חומרה: קריטי
תחום: אימות
תיאור: משתמשים שמנסים לאפס סיסמה דרך Gmail לא מקבלים את המייל. בכל שאר הספקים (Outlook, Yahoo, ארגוני) המייל מגיע. נראה שה-IP של שרת המייל שלנו נחסם על ידי Google.
השפעה: ~40% ממשתמשים שמנסים לאפס סיסמה (Gmail הוא הספק הנפוץ ביותר).
---
```

Continue this pattern for bugs 006–050. Distribute as follows:
- BUG-006 to BUG-012: Performance issues (slow loading, timeouts, memory)
- BUG-013 to BUG-020: UI/UX issues (layout, mobile, accessibility)
- BUG-021 to BUG-030: Integration issues (Jira sync, GitHub webhooks, Zapier)
- BUG-031 to BUG-038: Notification issues (email, Slack, in-app)
- BUG-039 to BUG-044: Authentication/permissions issues
- BUG-045 to BUG-050: Data/export issues (reports, CSV, API)

Vary severity: ~5 קריטי, ~15 גבוה, ~20 בינוני, ~10 נמוך

**Step 2: Verify**
- 50 bugs present
- Mix of severities and areas
- Each has all required fields
- Hebrew throughout

---

## Task 4: Create example-files/user-feedback.txt

**Files:**
- Create: `PFP-Workshop/example-files/user-feedback.txt`

**Step 1: Write the file**

30 feedback items from Telos users. Mix of: support tickets, app store reviews, NPS follow-ups, in-app feedback. Hebrew. Format:

```
---
מקור: [תמיכה / חנות אפליקציות / NPS / פידבק באפליקציה]
תאריך: [2026 date]
משתמש: [first name, company type]
ציון: [1-10 if NPS, ⭐ rating if app store, N/A otherwise]
פידבק:
[2-4 sentences of feedback]
---
```

Examples:

```
---
מקור: NPS
תאריך: 2026-02-08
משתמש: אורי, חברת הייטק בינונית
ציון: 4
פידבק:
המוצר בסיסי עובד טוב, אבל אני מבלה יותר מדי זמן בלייצא דוחות ידנית ל-Excel. הייתי מצפה שיהיה dashboard מובנה שאני יכול לשלוח למנהלים שלי בלחיצת כפתור. בנוסף, האינטגרציה עם Jira מתפרקת לפחות פעם בשבוע ואנחנו צריכים לחבר מחדש.
---

---
מקור: תמיכה
תאריך: 2026-02-13
משתמש: שירה, חברת פינטק
ציון: N/A
פידבק:
פתחנו טיקט כי המשימות שהוקצו ל-sprint לא מופיעות בלוח הבקרה של הסיפרינט. ראינו את זה אצל 3 אנשים בצוות. נסינו לרענן ולהתנתק אבל הבעיה נמשכת. זה חוסם אותנו מלעשות sprint planning.
---

---
מקור: חנות אפליקציות
תאריך: 2026-02-09
משתמש: יואב
ציון: ⭐⭐
פידבק:
האפליקציה לנייד שבורה לחלוטין. לא יכול ליצור משימות, הלוח הבקרה מתרסק, וההתראות לא מגיעות. בדסקטופ הכל בסדר אבל מי עובד רק מהמחשב? אנחנו צריכים את הנייד. מאוד מאכזב.
---
```

Continue for items 4–30. Cover themes:
- Items 4-10: Feature requests (dashboards, reporting, templates)
- Items 11-18: Integration complaints (Slack, Jira, GitHub)
- Items 19-24: Mobile experience issues
- Items 25-28: Onboarding confusion
- Items 29-30: Positive feedback (for balance)

**Step 2: Verify**
- 30 items present
- Mix of sources and tones
- Some bugs overlap with bug-reports.txt (this is realistic and intentional — shows the agent can correlate)

---

## Task 5: Create example-files/sprint-backlog.txt

**Files:**
- Create: `PFP-Workshop/example-files/sprint-backlog.txt`

**Step 1: Write the file**

20 candidate items for Sprint 48 planning. Mix of features, bugs, tech debt, and discovery tasks. Hebrew. Format:

```
---
מזהה: ITEM-[number]
כותרת: [title]
סוג: [פיצ'ר / תיקון באג / חוב טכני / גילוי]
הערכת מאמץ: [XS / S / M / L / XL]
קשר לבאגים: [BUG-xxx אם רלוונטי, אחרת N/A]
תיאור קצר: [1-2 sentences]
---
```

Examples:

```
---
מזהה: ITEM-001
כותרת: תיקון ביצועי לוח הבקרה — טעינה מהירה ל-50+ משימות
סוג: תיקון באג
הערכת מאמץ: L
קשר לבאגים: BUG-001
תיאור קצר: אופטימיזציה של שאילתות ה-DB ו-pagination בלוח הבקרה. המטרה: טעינה תחת 2 שניות לכל גודל חשבון.
---

---
מזהה: ITEM-002
כותרת: תיקון התראות Slack על דד-ליין
סוג: תיקון באג
הערכת מאמץ: S
קשר לבאגים: BUG-002
תיאור קצר: מציאת הסיבה לאי-שליחת webhooks לאחר v2.4.1 ותיקון. הוספת monitoring על כשלי webhook.
---

---
מזהה: ITEM-003
כותרת: Dashboard שבועי לייצוא אוטומטי
סוג: פיצ'ר
הערכת מאמץ: XL
קשר לבאגים: N/A
תיאור קצר: PM יוכל להגדיר דוח שבועי שנשלח אוטומטית למנהלים. פורמטים: PDF, Slack message. מגיע מ-NPS feedback ו-CS requests חוזרים.
---
```

Continue for items 4–20.

**Step 2: Verify**
- 20 items present
- Mix of types and effort sizes
- Several items link to bug-reports.txt bugs

---

## Task 6: Create workshop-commands.md

**Files:**
- Create: `PFP-Workshop/workshop-commands.md`

**Step 1: Write the file**

```markdown
# פקודות לסדנה — Copy-Paste מוכן

## שלב 1: התקנה

```bash
npm install -g @anthropic-ai/claude-code
claude --version
claude
```

## שלב 2: Clone עם Claude Code

הדבק את זה ל-Claude Code:
```
תריץ עבורי: git clone https://github.com/[REPO-URL] workshop
cd workshop
```

## שלב 3: התיישרות עם הפרויקט

```
קרא את קובץ CLAUDE.md ותסכם לי את הפרויקט שאנחנו עובדים עליו.
```

## שלב 4: הכרת הסוכנים והסקילים

```
מה הסוכנים שיש לי בתיקיית .claude/agents? תסביר כל אחד במשפט אחד.
```

```
מה הסקילים שיש לי בתיקיית .claude/skills? תסביר כל אחד במשפט אחד.
```

## שלב 5: ניתוח הבאגים (Hands-on Step 1)

```
תנתח את קובץ example-files/bug-reports.txt ותיצור דוח עדיפויות.
חשוב להתחשב בחומרת הבאג, מספר המשתמשים המושפעים, ואזור הבעיה.
הוצא: TOP 10 באגים לתיקון עם הסבר, ו-5 באגים לדחות.
```

## שלב 6: עדכון לבעלי עניין (Hands-on Step 2)

```
/write-stakeholder-update
```

כשהסקיל שואל — ספקו:
- קהל: VP Product + CTO
- נושא: סיכום עדיפויות באגים לשבוע הקרוב
- פורמט: הודעת Slack קצרה (עד 150 מילה)
- מבוסס על: דוח הבאגים שיצרנו עכשיו

## בונוס — אם נשאר זמן

```
תנתח גם את example-files/user-feedback.txt ותאמר לי אם יש נושאים שמתחברים לבאגים שמצאנו.
```
```

**Step 2: Verify**
- All commands are copy-paste ready
- Hebrew throughout
- Steps match the agenda order
- Repo URL placeholder marked clearly (to be updated after repo creation)

---

## Task 7: Adapt agents from Meetup 4

**Files:**
- Create: `PFP-Workshop/.claude/agents/user-feedback-analyzer.md`
- Create: `PFP-Workshop/.claude/agents/meeting-summary.md`
- Create: `PFP-Workshop/.claude/agents/sprint-backlog-prioritizer.md`

### Step 1: Copy and adapt user-feedback-analyzer.md

Source: `Meetup-4-IRL-Workshop/templates/agents/user-feedback-analyzer.md`

Copy the file as-is. Then change the final paragraph of "Best Practices" to add:

```markdown
- **Company Context First**: Always refer to the CLAUDE.md file to understand the product, team structure, and current priorities before analyzing. Frame findings in terms of business impact, not just user sentiment.
- **Connect to Backlog**: When themes match known bugs or backlog items, call that out explicitly.
```

### Step 2: Copy meeting-summary.md as-is

Source: `Meetup-4-IRL-Workshop/templates/skills/meeting-summary.md`

No changes needed. Copy exactly.

### Step 3: Write sprint-backlog-prioritizer.md (new agent)

```markdown
---
name: sprint-backlog-prioritizer
description: Use this agent when you need to prioritize a sprint backlog or list of candidate items for an upcoming sprint. Activated when: user provides a backlog file or list of items and wants a recommended sprint scope. The agent considers effort estimates, business impact, dependencies, and bug severity.
model: inherit
color: green
---

You are an expert Sprint Planning Facilitator with deep experience in agile product management for B2B SaaS companies. Your job is to help PMs decide what goes into the next sprint.

## Your Process

1. **Read the CLAUDE.md** to understand the product, current quarter goals, and sprint cadence.

2. **Ingest the backlog**: Read the provided file or list. Extract all items with their type, effort, and any linked bugs.

3. **Score each item** using this criteria:
   - **Business Impact** (1-3): Does it directly affect churn, activation, or revenue goals?
   - **User Pain** (1-3): How many users are affected? How severely?
   - **Effort** (1-3): XS=1, S=1, M=2, L=3, XL=3
   - **Priority Score** = (Business Impact + User Pain) / Effort

4. **Recommend sprint scope**:
   - Assume a 2-week sprint with ~30 story points (adjust if CLAUDE.md says otherwise)
   - XS=1pt, S=2pt, M=3pt, L=5pt, XL=8pt
   - Flag dependencies between items

5. **Output a sprint recommendation**:

```markdown
# המלצת Sprint [number] — [date]

## מה להכניס לספרינט (סה"כ: X נקודות)

| מזהה | כותרת | סוג | נקודות | נימוק |
|------|-------|-----|--------|-------|
| ITEM-XXX | ... | ... | X | ... |

## מה לדחות לספרינט הבא

| מזהה | כותרת | סיבה לדחייה |
|------|-------|------------|
| ITEM-XXX | ... | ... |

## תלויות שחשוב לשים לב אליהן
- [dependency note]

## שאלות פתוחות לפלנינג
- [ ] [question]
```

## Guiding Principles
- Critical bugs (that affect many users) almost always take priority over new features
- Don't over-commit — a focused sprint beats an overloaded one
- Always flag items that need more discovery before they can be estimated
```

**Step 4: Verify**
Open each agent file. Confirm the YAML front matter is valid, description is clear, and body instructions are actionable.

---

## Task 8: Adapt skills from Meetup 4 + create new skill

**Files:**
- Create: `PFP-Workshop/.claude/skills/prioritize.md`
- Create: `PFP-Workshop/.claude/skills/create-user-stories.md`
- Create: `PFP-Workshop/.claude/skills/write-stakeholder-update.md`

### Step 1: Copy prioritize.md as-is

Source: `Meetup-4-IRL-Workshop/templates/skills/prioritize.md`
No changes needed. Copy exactly.

### Step 2: Copy create-user-stories.md as-is

Source: `Meetup-4-IRL-Workshop/templates/skills/user-stories.md`
Copy as-is, rename to `create-user-stories.md`.

### Step 3: Write write-stakeholder-update.md (new skill)

```markdown
# Skill: /write-stakeholder-update

## Purpose
Turn a technical report, prioritization doc, or analysis into a clear, actionable stakeholder update — ready to send via Slack, email, or paste into a doc.

## Trigger
```
/write-stakeholder-update
```

## What It Does
1. Asks: who is the audience, what's the context, what format?
2. Takes the most recent output in the conversation (or a file you point to)
3. Rewrites it as a stakeholder update in the requested format
4. Saves to file

## Skill Instructions

When the user triggers `/write-stakeholder-update`:

### Step 1: Get Context
```
כמה שאלות מהירות:

1. **קהל היעד**: מי מקבל את העדכון? (VP Product / CTO / צוות פיתוח / לקוח)
2. **נושא**: על מה אנחנו מדווחים? (באגים / ספרינט / משוב משתמשים / אחר)
3. **פורמט**:
   - הודעת Slack קצרה (עד 150 מילה)
   - מייל (עד 300 מילה)
   - עדכון Notion / Confluence (מסמך מובנה)
4. **על בסיס מה**: מה אני אעבוד עליו? (התוצר מהשלב הקודם / קובץ ספציפי)
```

### Step 2: Generate Update

**For Slack (short):**
```markdown
*עדכון [נושא] — [תאריך]*

📌 *מה מצאנו:*
[2-3 bullet points — the key findings]

⚡ *מה עושים:*
[1-3 bullet points — concrete actions, with owners if known]

❓ *צריך החלטה:*
[1 item if relevant, else omit this section]

— [שם] | [תאריך]
```

**For Email:**
```markdown
נושא: [subject line]

היי [name],

[1 sentence context — why this email]

**מה מצאנו:**
[3-5 bullets]

**המלצת הצוות:**
[2-3 bullets with actions]

**מה אנחנו צריכים ממך:**
[1 specific ask — decision, approval, info]

תודה,
[שם]
```

**For Notion/Confluence:**
```markdown
# עדכון [נושא] — [תאריך]

## רקע
[1-2 sentences]

## ממצאים עיקריים
| נושא | פירוט | עדיפות |
|------|-------|--------|
| ... | ... | ... |

## המלצות
1. [action + owner + timeline]
2. [action + owner + timeline]

## שאלות פתוחות
- [ ] [question]

## צעדים הבאים
- [ ] [next step + deadline]
```

### Step 3: Save and Confirm
```
העדכון מוכן!

מותאם ל: [audience]
פורמט: [format]
אורך: [word count]

שמור ב: updates/[date]-[topic]-update.md

מוכן לשלוח! 📤
```

## Example Usage

**User:**
```
/write-stakeholder-update
```
→ [Claude asks questions]
→ User: "קהל: VP Product. נושא: עדיפויות באגים. פורמט: Slack. מבוסס על הניתוח שעשינו."

**Output:**
```
*עדכון באגים — פברואר 2026*

📌 *מה מצאנו:*
• 5 באגים קריטיים מחייבים טיפול מיידי — בעיקר אימות ונייד
• אינטגרציית Slack שבורה — משפיעה על 1,200 משתמשים
• ביצועי לוח הבקרה — 340 לקוחות enterprise מושפעים

⚡ *מה עושים:*
• BUG-005 (איפוס סיסמה Gmail) → תיקון דחוף השבוע — Avi
• BUG-002 (Slack webhooks) → Sprint 48 — צוות integrations
• BUG-001 (ביצועים) → אופטימיזציה Sprint 48 — team lead

— [שם] | 20.02.2026
```

## Time Saved
- Manual stakeholder update: 30-45 minutes
- With /write-stakeholder-update: 3-5 minutes
- **Savings: ~35 minutes per update**
```

**Step 2: Verify**
Open each skill file. Confirm it starts with the `# Skill:` header, has a trigger, and has clear output examples.

---

## Task 9: Create Presentation HTML

**Files:**
- Create: `PFP-Workshop/pfp-workshop-presentation.html`

**Step 1: Copy Meetup 4 presentation as base**

Source: `Meetup-4-IRL-Workshop/meetup-4-presentation.html`

Copy the entire file to `PFP-Workshop/pfp-workshop-presentation.html`. Keep all CSS, Reveal.js CDN links, and the overall structure intact.

**Step 2: Replace all slide content**

Remove all existing `<section>` elements inside the Reveal.js `<div class="slides">` container. Replace with exactly 9 slides:

**Slide 1 — Title**
```html
<section>
  <h1>סדנת Claude Code</h1>
  <h2>Product for Product</h2>
  <p>בעוד 90 דקות יהיה לכם:</p>
  <ul>
    <li>✅ Claude Code מותקן ועובד</li>
    <li>✅ Toolkit מקצועי מוכן לשימוש</li>
    <li>✅ דוח עדיפויות באגים מוכן</li>
    <li>✅ עדכון מוכן לשליחה ל-VP</li>
  </ul>
  <p><em>בואו נתחיל</em> 🚀</p>
</section>
```

**Slide 2 — Installation**
```html
<section>
  <h2>⚙️ התקנה</h2>
  <pre><code>npm install -g @anthropic-ai/claude-code</code></pre>
  <pre><code>claude --version</code></pre>
  <pre><code>claude</code></pre>
  <p>בדקו: כתבו <code>שלום, מה שלומך?</code> → Claude עונה בעברית ✅</p>
</section>
```

**Slide 3 — Git & GitHub**
```html
<section>
  <h2>📚 מה זה Git ו-GitHub?</h2>
  <div class="visual-card">
    <p><strong>Git</strong> = מערכת גרסאות מקומית</p>
    <p>כמו "היסטוריית שמירות" לכל קובץ</p>
  </div>
  <div class="visual-card">
    <p><strong>GitHub</strong> = המדף המשותף בענן</p>
    <p>כולם מורידים מאותו מקום, תמיד עדכני</p>
  </div>
  <p>🎯 היום: נוריד את ה-Toolkit שלכם ישירות מ-GitHub</p>
  <p>Claude Code יריץ את הפקודה בשבילכם</p>
</section>
```

**Slide 4 — Clone via Claude Code**
```html
<section>
  <h2>📥 מורידים את ה-Toolkit</h2>
  <p>כתבו ב-Claude Code:</p>
  <pre><code>תריץ עבורי:
git clone [REPO-URL] workshop
cd workshop</code></pre>
  <br>
  <p class="big-icon">💡</p>
  <p><em>"שימו לב — לא הקלדתי פקודת git אחת.<br>Claude Code הריץ אותה בשבילי."</em></p>
</section>
```

**Slide 5 — What is CLAUDE.md**
```html
<section>
  <h2>📋 מה זה CLAUDE.md?</h2>
  <div class="visual-card">
    <p>🧑‍💼 דמיינו שקיבלתם עובד חדש לצוות</p>
    <p>אתם נותנים לו מסמך onboarding:</p>
    <p>מי אנחנו, מה אנחנו בונים, מי הלקוחות</p>
  </div>
  <br>
  <div class="visual-card">
    <p>📄 CLAUDE.md = מסמך ה-onboarding של Claude</p>
    <p>Claude קורא אותו אוטומטית בכל session</p>
    <p>יודע הכל על הפרויקט שלכם — <strong>ללא הסבר חוזר</strong></p>
  </div>
</section>
```

**Slide 6 — Agents vs Skills**
```html
<section>
  <h2>🤖 Agents מול Skills</h2>
  <table style="font-size:0.75em; width:100%">
    <tr>
      <th></th>
      <th>Agents 🤖</th>
      <th>Skills ⚡</th>
    </tr>
    <tr>
      <td><strong>מי מפעיל</strong></td>
      <td>Claude מחליט מתי לקרוא</td>
      <td>אתם — /skill-name</td>
    </tr>
    <tr>
      <td><strong>מתאים ל</strong></td>
      <td>ניתוח פתוח, עבודה אוטונומית</td>
      <td>תוצר ידוע מראש, תבנית קבועה</td>
    </tr>
    <tr>
      <td><strong>דוגמה</strong></td>
      <td>"נתח 50 באגים ותעדף"</td>
      <td>/write-stakeholder-update</td>
    </tr>
  </table>
  <br>
  <p>💡 <em>הם עובדים יחד: Agent מנתח → Skill מפיק</em></p>
</section>
```

**Slide 7 — Agents detail**
```html
<section>
  <h2>🤖 הסוכנים שלכם היום</h2>
  <ul>
    <li><strong>bug-priority-analyzer</strong> — מנתח באגים ומעדף לפי חומרה והשפעה</li>
    <li><strong>user-feedback-analyzer</strong> — מנתח פידבק משתמשים ומוצא דפוסים</li>
    <li><strong>sprint-backlog-prioritizer</strong> — ממליץ מה להכניס לספרינט הבא</li>
    <li><strong>meeting-summary</strong> — הופך נוטס לסיכום מקצועי עם action items</li>
  </ul>
  <p>📁 נמצאים ב: <code>.claude/agents/</code></p>
</section>
```

**Slide 8 — The Challenge**
```html
<section>
  <h2>⏰ תרחיש יום שני בבוקר</h2>
  <div class="visual-card">
    <p>08:30 — פלנינג ספרינט בעוד שעה וחצי</p>
    <p>50 באגים פתוחים ב-Jira</p>
    <p>30 פידבקים חדשים ממשתמשים</p>
    <p>ה-VP שואל: "מה עדיפויות השבוע?"</p>
  </div>
  <br>
  <p>🎯 <strong>המשימה שלכם:</strong></p>
  <p>דוח עדיפויות + עדכון ל-VP</p>
  <p>בעוד 25 דקות</p>
  <p class="big-icon">בואו נעשה את זה 💪</p>
</section>
```

**Slide 9 — Wrap Up**
```html
<section>
  <h2>🎉 מה עשיתם היום</h2>
  <ul>
    <li>✅ Claude Code מותקן</li>
    <li>✅ הורדתם Toolkit מ-GitHub</li>
    <li>✅ הבנתם CLAUDE.md, Agents ו-Skills</li>
    <li>✅ דוח עדיפויות ב-3 דקות</li>
    <li>✅ עדכון ל-VP מוכן לשליחה</li>
  </ul>
  <br>
  <p>🎯 <strong>מחר בבוקר:</strong></p>
  <p>פתחו את Claude Code עם הפרויקט האמיתי שלכם</p>
  <p>שנו את CLAUDE.md → והתחילו</p>
  <br>
  <p>🔗 ה-Toolkit: <code>[REPO-URL]</code></p>
</section>
```

**Step 3: Update title tag**
Change `<title>` to: `סדנת Claude Code — Product for Product`

**Step 4: Verify**
Open in browser. Check:
- [ ] RTL renders correctly
- [ ] All 9 slides present
- [ ] Navigation works (arrow keys)
- [ ] Code blocks readable
- [ ] Table on slide 6 fits on screen

---

## Task 10: Create WORKSHOP-PLAN.md

**Files:**
- Create: `PFP-Workshop/WORKSHOP-PLAN.md`

**Step 1: Write the full speaker plan**

Write a detailed speaker plan following the exact format of `Meetup-4-IRL-Workshop/FINAL-AGENDA.md`. Include:

- Header with date, duration (90 min), participants (~30), assistant (1)
- Timeline table overview
- Each section with: time, goal, exact speaker notes, commands to run, what to show on screen
- "If running behind" fallbacks for each section
- Energy notes (which moments are high-energy, which are calm)
- Pre-workshop checklist (projector, power strips, repo URL ready, fonts enlarged, etc.)

Cover all 7 sections from the agenda:
1. Installation (00:00–00:15)
2. Git + Clone (00:15–00:25)
3. Tour CLAUDE.md (00:25–00:35)
4. Tour Agents vs Skills (00:35–00:50)
5. Hands-on Step 1: bug triage (00:50–01:05)
6. Hands-on Step 2: stakeholder update (01:05–01:15)
7. Share + Wrap up (01:15–01:30)

Key speaker note to include verbatim at the clone moment:
> "שימו לב — לא הקלדתי פקודת git אחת. Claude Code הריץ אותה בשבילי. זה בדיוק הנקודה."

Key speaker note for the triage moment:
> "זה מה שהייתם עושים שעתיים ביום שני בבוקר. זה לקח 3 דקות. כל שני."

**Step 2: Verify**
Read through the plan. Confirm every section has: time, goal, speaker notes, what's on screen, and a fallback.

---

## Post-Creation Checklist

After all tasks are complete:

- [ ] All files created and verified
- [ ] Presentation opens in browser with correct RTL + 9 slides
- [ ] workshop-commands.md updated with real repo URL (after GitHub repo creation)
- [ ] Slide 4 and Slide 9 updated with real repo URL
- [ ] `bug-priority-analyzer.md` added manually by Yonatan to `.claude/agents/`
- [ ] GitHub repo created and all files pushed (separate action by Yonatan)
- [ ] Test the full hands-on flow: clone → read CLAUDE.md → run bug agent → run skill

---

*Plan version: 1.0*
*Created: 2026-02-20*
*Based on design doc: docs/plans/2026-02-20-pfp-workshop-design.md*
