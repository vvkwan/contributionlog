# Contribution 1: Migrate math/base/special packages from relative tolerance testing to ULP difference testing

**Contribution Number:** 1 
**Student:** Valerie Kwan 
**Issue:** [[GitHub issue link]  ](https://github.com/stdlib-js/stdlib/issues/11352)
**Status:** Phase III in progress

---

## Why I Chose This Issue

Recently, I have been working on a few Javascript projects, specifically relating to machine learning, 
so I decided to look for an issue in a project that was developed in this language. 
I chose this issue to gain more experience in understanding tests. I have written basic unit tests before, 
but I am hoping to gain more in-depth knowledge in testing mathematical functions.

---

## Understanding the Issue

### Problem Description

Previously, testing for math/base/special packages was done with relative tolerance, where the absolute difference between the expected value and the 
result was calculated and checked whether it was within tolerance. However, relative tolerance is not a completely
reliable method. Instead, the issue proposes to replace that with an assert function (@stdlib/assert/is-almost-same-value) that checks whether the two inputs
are within a specified number of ULP units away from each other.

I chose the kernel-betaincinv package that hasn't been tackled yet and this repository asks that first-time contributors do
not comment and claim issues.

### Expected Behavior

The expected test should make use of the function stated above and remove all references to relative testing.

### Current Behavior

As explained in the problem description, testing for this package currently uses relative tolerance.

### Affected Components

The kernel-betaincinv test file

---

## Reproduction Process

### Environment Setup

N/A; I followed the development guideline set by stdlib-js.

### Steps to Reproduce

1. Run make test
2. [Step 2]
3. [Observed result]

### Reproduction Evidence

- **Commit showing reproduction:** [Link to commit in your fork]
- **Screenshots/logs:** [If applicable]
- **My findings:** [What you discovered during reproduction]

---

## Solution Approach

### Analysis

[Your analysis of the root cause - what's causing the issue?]

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
