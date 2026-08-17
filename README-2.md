# Contribution 1: Migrate `math/base/special` packages from relative tolerance testing to ULP difference testing

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

1. Run `make TESTS_FILTER=".*/math/base/special/kernel-betaincinv/.*" test`
2. Ensure all tests pass.

### Reproduction Evidence

- **Commit showing reproduction:** [[Link to commit in your fork]](https://github.com/vvkwan/stdlib/tree/test-kernel-betaincinv-ulp)
- **Screenshots/logs:** N/A
- **My findings:** N/A

---

## Solution Approach

### Analysis

N/A

### Proposed Solution

I looked at the code provided in the issue description, which assumed a default of 1 for the ULP bound; for the package I chose, the ULP bound needed to be increased until all tests passed. I found an example of previously merged in code that previously had a multiplier for EPS for relative tolerance testing. The migrated ULP difference testing had an increased ULP bound, so I knew that I needed to increase the ULP bound until the tests passed.

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** The testing in this package previously relied on relative tolerance testing.

**Match:** Other contributors have already migrated many packages to ULP testing, so I am able to use those as references.

**Plan:** [Step-by-step implementation plan]
1. Remove all references of abs and EPS in the test.js file.
2. Replace it with the line specified in the issue description; `t.strictEqual( isAlmostSameValue( y, expected[ i ], 1 ), true, 'returns expected value' );`
3. Ensure that the ULP bound is correct.

**Implement:** [[Link to your branch/commits as you work]](https://github.com/vvkwan/stdlib/tree/test-kernel-betaincinv-ulp)

**Review:** I followed the clear contributing instructions outlined in their [[CONTRIBUTING.md]](https://github.com/stdlib-js/stdlib/blob/develop/CONTRIBUTING.md). 

**Evaluate:** The tests pass, so I assume it worked.

---

## Testing Strategy

### Unit Tests

- [ ] N/A; I am modifying the tests for a package, so it was part of the implementation process to run tests.
### Integration Tests

- [ ] N/A

### Manual Testing

N/A

---

## Implementation Notes

### Week [X] Progress

N/A

### Week [Y] Progress

N/A

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** I initially was confused on whether or not to significantly increase the ULP bound when it was only failing for one test, but I ran the previous code with a lower multiplier on EPS for relative testing and the only test that failed was that one, so I came to the conclusion that that was most likely a deliberate choice by the test creator.

---

## Pull Request

**PR Link:** [[GitHub PR URL when submitted]](https://github.com/stdlib-js/stdlib/pull/14349)

**PR Description:** 

Resolves a part of #11352 .

Description
What is the purpose of this pull request?

This pull request:

Migrates tests in math/base/special/kernel-betaincinv from relative tolerance testing to ULP difference testing.
All fixtures pass when the ULP bound is 10 except for index 1818, which requires a ULP bound of 20; this fixture case also had the tightest margin under the previous 15.0 * EPS tolerance.
Related Issues
Does this pull request have any related issues?

This pull request has the following related issues:

[RFC]: Migrate math/base/special packages from relative tolerance testing to ULP difference testing (tracking issue) #11352
Questions
Any questions for reviewers of this pull request?

No.

Other
Any other information relevant to this pull request? This may include screenshots, references, and/or implementation notes.

No.

Checklist
Please ensure the following tasks are completed before submitting this pull request.

 Read, understood, and followed the contributing guidelines.
AI Assistance
When authoring the changes proposed in this PR, did you use any kind of AI assistance?

 Yes
 No
If you answered "yes" above, how did you use AI assistance?

 Code generation (e.g., when writing an implementation or fixing a bug)
 Test/benchmark generation
 Documentation (including examples)
 Research and understanding
Disclosure
If you answered "yes" to using AI assistance, please provide a short disclosure indicating how you used AI assistance. This helps reviewers determine how much scrutiny to apply when reviewing your contribution. Example disclosures: "This PR was written primarily by Claude Code." or "I consulted ChatGPT to understand the codebase, but the proposed changes were fully authored manually by myself.".

I consulted AI to understand the codebase, specifically the purpose and migration approach of the issue and this package, but the proposed changes were authored by myself.

@stdlib-js/reviewers

**Maintainer Feedback:**
- [8/17/26]: I got a review:5, which seems to mean the reviewer was satisfied with the changes made and that I followed the CONTRIBUTING.md.

**Status:** [Merged]

---

## Learnings & Reflections

### Technical Skills Gained

I learned about testing and the different considerations people have to make when adapting different packages to a change; thankfully, this issue had a lot of examples of the migration approach applied and I was able to look at a lot of them as reference.

### Challenges Overcome

I wrote about this in my approach section, but I thought this was going to be an extremely straightforward migration, but I had to take into consideration whether or not the case that was not passing was intentionally an outlier or needed a special designation.

### What I'd Do Differently Next Time

I don't believe there is anything I would do significantly differently, since this was an issue that I thought was within my capabilities.

---

## Resources Used

N/A
