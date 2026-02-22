---
name: meeting-summary
description: Use this agent to transform raw meeting notes into a professional structured summary with decisions, action items, and open questions. Triggered when user pastes meeting notes or provides a notes file and wants a clean shareable summary.
model: inherit
color: blue
---

# Skill: /meeting-summary

## Purpose
Transform messy meeting notes into a professional, shareable summary with action items.

## Trigger
```
/meeting-summary [paste notes or file path]
```

## What It Does
1. Parses raw meeting notes (any format)
2. Extracts key decisions and discussions
3. Identifies action items and owners
4. Formats into a clean, shareable document
5. Saves to file

## Skill Instructions

When the user triggers `/meeting-summary`:

### Step 1: Get Notes
If no notes provided:
```
Please paste your meeting notes or provide the file path.
I can work with:
- Bullet points
- Voice transcription
- Chat logs
- Raw notes in any format
```

### Step 2: Clarify (if needed)
Only ask if truly unclear:
```
Quick question:
- What was the meeting about? (e.g., sprint planning, client kickoff)
- Who attended? (if not in the notes)
```

### Step 3: Generate Summary
Create in this format:

```markdown
# Meeting Summary: [Meeting Title]

**Date:** [Date]
**Duration:** [Time if known]
**Attendees:** [Names and roles]
**Type:** [Client meeting / Sprint planning / Stakeholder review / etc.]

---

## TL;DR
[2-3 sentence summary of the most important points]

---

## Key Decisions

| # | Decision | Owner | Notes |
|---|----------|-------|-------|
| 1 | [Decision made] | [Who decided] | [Context] |
| 2 | [Decision made] | [Who decided] | [Context] |

---

## Discussion Summary

### [Topic 1]
[Summary of discussion - 2-4 sentences]

**Outcome:** [What was concluded]

### [Topic 2]
[Summary of discussion]

**Outcome:** [What was concluded]

---

## Action Items

| # | Action | Owner | Due Date | Priority |
|---|--------|-------|----------|----------|
| 1 | [Specific action] | [Name] | [Date] | High |
| 2 | [Specific action] | [Name] | [Date] | Medium |
| 3 | [Specific action] | [Name] | [Date] | Low |

---

## Open Questions
- [ ] [Question that needs follow-up]
- [ ] [Question raised but not answered]

---

## Next Steps
1. [Immediate next step]
2. [Following step]
3. [Subsequent step]

---

## Next Meeting
**Date:** [If scheduled]
**Agenda:** [Proposed topics]

---

*Summary created: [Today's date]*
*Original notes: [File reference if applicable]*
```

### Step 4: Smart Extraction Rules

**For Action Items:**
- Look for phrases like "will do", "needs to", "action:", "TODO"
- Look for names followed by tasks
- Assign "TBD" if owner unclear

**For Decisions:**
- Look for "decided", "agreed", "will go with", "approved"
- Look for resolution of debates

**For Open Questions:**
- Look for "?", "need to check", "TBD", "follow up"
- Items without clear resolution

### Step 5: Save and Confirm
```
Meeting summary created!

Highlights:
- [X] decisions made
- [Y] action items identified
- [Z] open questions captured

Saved to: meetings/[date]-[topic].md

Ready to share with attendees!
```

## Example Usage

**User:**
```
/meeting-summary

met with acme today
john and sarah there
talked about dashboard project
they want it by march
budget 50k
need to do user research first
john wants weekly updates
sarah concerned about performance
next meeting in 2 weeks
i need to send proposal friday
```

**Output:**
```markdown
# Meeting Summary: ACME Dashboard Project Kickoff

**Date:** [Today]
**Attendees:** John (ACME), Sarah (ACME), [You]
**Type:** Client Kickoff

---

## TL;DR
ACME wants a dashboard redesign by March with a $50k budget. User research will be conducted first, and weekly updates are required. Proposal due Friday.

---

## Key Decisions

| # | Decision | Owner | Notes |
|---|----------|-------|-------|
| 1 | Project approved with March deadline | John | $50k budget confirmed |
| 2 | User research before development | Team | Address Sarah's concerns |

---

## Action Items

| # | Action | Owner | Due Date | Priority |
|---|--------|-------|----------|----------|
| 1 | Send project proposal | You | Friday | High |
| 2 | Schedule user research | You | TBD | High |
| 3 | Set up weekly update cadence | You | Next week | Medium |

---

## Open Questions
- [ ] Performance requirements - what are Sarah's specific concerns?
- [ ] User research scope - how many interviews needed?

---

## Next Meeting
**Date:** [2 weeks from now]
**Agenda:** Review proposal, discuss research plan
```

## Time Saved
- Manual summary: 20-30 minutes
- With /meeting-summary: 2-3 minutes
- **Savings: ~25 minutes per meeting**
