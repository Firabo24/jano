# ASSESSMENT_AGGREGATE_ARCHITECTURE.md

**Version:** v0.1.0
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Boundary

Assessment Aggregate = Assessment Lifecycle + Findings + Finding Attribution + Clinical Meaning + Correction / Amendment Integrity.

## 2. Owns

Assessment lifecycle, findings, finding attribution, clinical meaning, correction/amendment integrity, and assessment-specific history.

## 3. Does Not Own

Encounter lifecycle, disposition, triage, clinical conclusion, treatment, medication, referral, or longitudinal condition ownership.

## 4. Lifecycle

```text
Not Started → Documenting → Completed
```

There is no Assessment Closed state in the current architecture.

## 5. Commands

Conceptual commands include Begin Assessment, Record Finding, Modify Finding where domain semantics permit, Correct Finding, Complete Assessment, Amend Assessment, and Late Assessment Documentation.

## 6. Correction Semantics

Correction is not amendment. Late Documentation means prior occurrence recorded later and does not automatically reopen Encounter.

## 7. Boundary Rule

The aggregate remains a separate strong candidate because it has an independently coherent invariant family and correction semantics, while continuing to avoid unnecessary cross-aggregate coordination.
