# Contribution 1: [Issue Title]

**Contribution Number:** 1
**Student:** Valerie Kwan  
**Issue:** [[GitHub issue link] ](https://github.com/esbmc/esbmc/issues/746) 
**Status:** Phase II In Progress

---

## Why I Chose This Issue

I chose this issue because I wanted to learn more about what ESBMC does in a manner that doesn't require me to understand any of the functionality. The issue talks about clang, which is a tool I have used previously, so I believe that I understand what they are asking for.

---

## Understanding the Issue

### Problem Description

The commenter asks for enabling color dumps in ESBMC's Clang frontend. ESBMC uses clang to print out errors, but currently, the errors are printed out in black and white.

### Expected Behavior

ESBMC should print out errors in color.

### Current Behavior

ESBMC errors are currently in black and white.

### Affected Components

The frontend portion

---

## Reproduction Process

### Environment Setup

n/a

### Steps to Reproduce

n/a not a bug

### Reproduction Evidence

- **Commit showing reproduction:** [Link to commit in your fork]
- **Screenshots/logs:** [If applicable]
- **My findings:** [What you discovered during reproduction]

---

## Solution Approach

### Analysis

The issue already talks about it, but instead of using purely dump(), the solution should use setShowColors() to enable colors.

### Proposed Solution

[High-level description of your fix approach]

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** [Restate the problem]

**Match:** [What similar patterns/solutions exist in the codebase?]

**Plan:** [Step-by-step implementation plan]
1. [Modify file X to do Y]
2. [Add function Z]
3. [Update tests]

**Implement:** [Link to your branch/commits as you work]

**Review:** [Self-review checklist - does it follow the project's contribution guidelines?]

**Evaluate:** [How will you verify it works?]

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
