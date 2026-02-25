---
name: write-stakeholder-update
description: Use when you need to turn a technical report, analysis, or prioritization doc into a clear stakeholder update ready to send via Slack, email, or Notion/Confluence.
---

# Skill: /write-stakeholder-update

## Purpose
Turn a technical report, prioritization doc, or analysis into a clear, actionable stakeholder update — ready to send via Slack, email, or paste into a doc.

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
