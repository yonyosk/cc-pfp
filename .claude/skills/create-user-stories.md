# Skill: /user-stories

## Purpose
Generate well-formatted user stories with acceptance criteria from a feature description or PRD.

## Trigger
```
/user-stories [feature description or PRD file path]
```

## What It Does
1. Reads the feature/PRD context
2. Identifies different user personas involved
3. Breaks down into atomic user stories
4. Adds acceptance criteria for each
5. Estimates story points
6. Outputs development-ready stories

## Skill Instructions

When the user triggers `/user-stories`:

### Step 1: Understand Context
If no file provided, ask:
```
What feature should I create user stories for?
Please describe the feature or point me to the PRD file.
```

If file provided, read and analyze it.

### Step 2: Identify Scope
Ask if not clear:
```
Quick clarifications:
1. Who are the main user types? (e.g., admin, regular user, guest)
2. What's the MVP scope? (all features or specific ones?)
3. Any story point scale preference? (1-13 Fibonacci / S-M-L-XL)
```

### Step 3: Generate Stories
Create stories in this format:

```markdown
# User Stories: [Feature Name]

**Source:** [PRD reference or description]
**Created:** [Date]
**Total Stories:** [Number]
**Total Points:** [Sum]

---

## Epic: [Epic Name]

### Story 1: [Short Title]

**ID:** US-001
**Priority:** Must Have
**Points:** [1/2/3/5/8]

> As a **[user type]**,
> I want **[action/capability]**,
> So that **[benefit/value]**.

**Acceptance Criteria:**
```gherkin
Given [precondition]
When [action]
Then [expected result]

Given [precondition]
When [alternative action]
Then [expected result]
```

**Notes:**
- [Any implementation notes]
- [Edge cases to consider]

**Dependencies:** [Other story IDs or "None"]

---

### Story 2: [Short Title]
[Same format...]

---

## Summary

| ID | Title | Priority | Points | Dependencies |
|----|-------|----------|--------|--------------|
| US-001 | [Title] | Must Have | 3 | None |
| US-002 | [Title] | Should Have | 5 | US-001 |

**Sprint Recommendation:**
- Sprint 1: US-001, US-002 (8 points)
- Sprint 2: US-003, US-004 (10 points)

---

## Out of Scope (Captured for Later)
- [Feature/story not included but noted]
- [Future enhancement]
```

### Step 4: Quality Check
Before outputting, verify:
- [ ] Each story is independent (can be developed alone)
- [ ] Each story has clear value statement
- [ ] Acceptance criteria are testable
- [ ] No story is too large (>8 points)
- [ ] Edge cases are covered

### Step 5: Save and Confirm
Save to `docs/user-stories-[feature].md`

```
Created [N] user stories for [Feature Name]

Total: [X] points across [Y] stories
Recommended sprints: [Z]

File saved to: docs/user-stories-[feature].md

Ready for sprint planning!
```

## Example Usage

**User:** `/user-stories checkout flow`

**Claude:**
```
I'll create user stories for the checkout flow. Let me confirm:

1. User types: Logged-in customers and guest checkout?
2. Payment methods: Credit card, PayPal, others?
3. Should I include error handling stories?
```

[User confirms]

**Output:**
```markdown
# User Stories: Checkout Flow

## Story 1: Add Items to Cart

**ID:** US-001
**Priority:** Must Have
**Points:** 3

> As a **shopper**,
> I want **to add products to my cart**,
> So that **I can purchase multiple items at once**.

**Acceptance Criteria:**
Given I am on a product page
When I click "Add to Cart"
Then the item appears in my cart
And the cart icon shows the updated count

Given I already have the item in cart
When I click "Add to Cart" again
Then the quantity increases by 1
...
```

## Time Saved
- Manual story writing: 1.5-2 hours per feature
- With /user-stories: 10-15 minutes
- **Savings: ~1.5 hours per feature**
