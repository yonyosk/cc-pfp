---
name: prioritize
description: Use when you need to prioritize a list of tasks, features, or bugs using established PM frameworks (Impact/Effort, RICE, MoSCoW).
---

# Skill: /prioritize

## Purpose
Prioritize a list of tasks, features, or bugs using established frameworks (Impact/Effort, RICE, MoSCoW).

## What It Does
1. Takes a list of items to prioritize
2. Asks clarifying questions if needed
3. Scores each item using selected framework
4. Creates visual prioritization matrix
5. Outputs ordered list with recommendations

## Skill Instructions

When the user triggers `/prioritize`:

### Step 1: Get Items
If no list provided:
```
What would you like me to prioritize?

You can:
- Paste a list of items
- Point me to a file (backlog.md, bugs.csv, etc.)
- Describe verbally

I can prioritize: features, bugs, tasks, projects, anything!
```

### Step 2: Choose Framework
```
Which prioritization approach?

1. **Impact/Effort Matrix** (Recommended for quick decisions)
   - Quick wins vs. major projects vs. avoid

2. **RICE Score** (Best for comparing many items objectively)
   - Reach × Impact × Confidence / Effort

3. **MoSCoW** (Best for release planning)
   - Must have / Should have / Could have / Won't have

4. **Let me decide** (I'll pick based on your list)
```

### Step 3: Generate Prioritization

```markdown
# Prioritization: [Context]

**Date:** [Today]
**Items:** [Number]
**Framework:** [Framework used]

---

## Quick Summary

**Do First:** [Top 3 items]
**Avoid/Defer:** [Bottom items]
**Key Trade-off:** [Main decision to make]

---

## Impact/Effort Matrix

         HIGH IMPACT
              │
  ┌───────────┼───────────┐
  │  Major    │   Quick   │
  │  Projects │   Wins    │
  │  (Plan)   │  (DO NOW) │
  │           │           │
──┼───────────┼───────────┼──
  │           │           │
  │   Time    │  Fill-    │
  │   Sinks   │  Ins      │
  │  (AVOID)  │  (Later)  │
  └───────────┼───────────┘
              │
         LOW IMPACT

  HIGH EFFORT ◄───► LOW EFFORT

---

## Detailed Prioritization

### Quick Wins (Do First)
*High Impact, Low Effort*

| Rank | Item | Impact | Effort | Notes |
|------|------|--------|--------|-------|
| 1 | [Item] | High | Low | [Why quick win] |
| 2 | [Item] | High | Low | [Notes] |

### Major Projects (Plan Carefully)
*High Impact, High Effort*

| Rank | Item | Impact | Effort | Notes |
|------|------|--------|--------|-------|
| 3 | [Item] | High | High | [Considerations] |
| 4 | [Item] | High | High | [Notes] |

### Fill-Ins (Do If Time)
*Low Impact, Low Effort*

| Rank | Item | Impact | Effort | Notes |
|------|------|--------|--------|-------|
| 5 | [Item] | Low | Low | [When to do] |

### Time Sinks (Avoid/Defer)
*Low Impact, High Effort*

| Item | Impact | Effort | Recommendation |
|------|--------|--------|----------------|
| [Item] | Low | High | Defer or eliminate |

---

## RICE Scores (if used)

| Rank | Item | Reach | Impact | Confidence | Effort | Score |
|------|------|-------|--------|------------|--------|-------|
| 1 | [Item] | [N] | [0-3] | [%] | [PM] | [Score] |
| 2 | [Item] | [N] | [0-3] | [%] | [PM] | [Score] |

**RICE Formula:** (Reach × Impact × Confidence) / Effort

---

## MoSCoW Classification (if used)

### Must Have (Non-negotiable)
- [Item] - [Justification]

### Should Have (Important)
- [Item] - [Justification]

### Could Have (Nice to have)
- [Item]

### Won't Have (This cycle)
- [Item] - [Why deferred]

---

## Recommended Sequence

### This Sprint/Week
1. [Item] - [Reason]
2. [Item] - [Reason]

### Next Sprint/Week
3. [Item] - [Reason]

### Later/Backlog
4. [Item]

---

## Trade-offs to Consider

**If you can only do 3 things:** [Items 1, 2, 3]
**If resources are limited:** Focus on [Items]
**If timeline is tight:** Prioritize [Items] because [reason]

---

## Open Questions

- [ ] [Question that affects prioritization]
- [ ] [Trade-off that needs stakeholder input]

---

*Prioritization completed: [Date]*
*Recommend re-prioritization: [When conditions change]*
```

### Step 4: Scoring Guidelines

**Impact Assessment:**
- **High:** Core functionality, revenue impact, many users
- **Medium:** Important feature, moderate benefit
- **Low:** Nice to have, few users, minimal impact

**Effort Assessment:**
- **Low:** 1-2 days, single component
- **Medium:** 3-5 days, some complexity
- **High:** 1+ weeks, multiple systems

### Step 5: Save and Confirm
```
Prioritization complete!

Summary:
- [N] items prioritized
- [X] quick wins identified
- [Y] items to defer/avoid

Top recommendation: Start with "[Item 1]" - highest impact, lowest effort

Saved to: planning/prioritization-[date].md
```

## Example Usage

**User:**
```
/prioritize
- Add dark mode
- Fix login bug
- Redesign dashboard
- Add export to PDF
- Improve search speed
- Build mobile app
```

**Output:**
```markdown
## Quick Summary

**Do First:**
1. Fix login bug (Critical - affects all users)
2. Improve search speed (High impact, medium effort)
3. Add export to PDF (Frequently requested)

**Avoid/Defer:**
- Build mobile app (Too large for current cycle)
- Redesign dashboard (Needs research first)

### This Sprint
1. **Fix login bug** - Critical, users being logged out
2. **Improve search speed** - High user value

### Next Sprint
3. **Add export to PDF** - Common request
4. **Add dark mode** - Low effort, nice UX win

### Later
5. **Redesign dashboard** - Needs discovery
6. **Build mobile app** - Major initiative, plan carefully
```

## Time Saved
- Manual prioritization: 1-2 hours
- With /prioritize: 5-10 minutes
- **Savings: ~1.5 hours per session**
