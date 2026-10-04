# Review and Approval Process

## 1. Drafting

A document is drafted against the approved baseline and its subject-specific boundary tests.

## 2. Architectural Review

Review examines:

- ownership and authority;
- consistency with parent architecture;
- overlap or leakage into other boundaries;
- lifecycle/invariant correctness where applicable;
- offline/safety/security/privacy implications;
- event/command/workflow distinctions;
- external integration boundaries;
- evidence and open questions.

## 3. Correction

Required corrections are recorded and the document remains Draft until the review decision explicitly promotes it.

## 4. Approval

Approval requires an explicit version/status decision. A document cannot become approved solely because another document references it or because implementation exists.

## 5. Supersession

When an approved document is replaced, the prior version remains traceable and the new document identifies the superseding relationship.

## 6. Current package rule

Only documents in `01_CANONICAL_BASELINE` are treated as approved architectural authority in this updated pack.
