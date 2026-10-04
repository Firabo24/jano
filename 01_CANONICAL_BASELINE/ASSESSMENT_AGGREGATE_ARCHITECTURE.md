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
## 8. Why Assessment Is a Separate Aggregate

The current approved baseline treats Assessment as a secondary aggregate because its invariant family can be analyzed independently of the Encounter lifecycle while remaining Encounter-scoped.

Its boundary is:

```text
Assessment Lifecycle
+
Findings
+
Finding Attribution
+
Clinical Meaning
+
Correction / Amendment Integrity
```

## 9. Assessment Lifecycle

```text
Not Started
     ↓
Documenting
     ↓
Completed
```

There is no Assessment Closed state in the current baseline.

## 10. Findings

An Assessment Finding is part of the Assessment model. Not every finding is an aggregate. Finding attribution, clinical meaning, and correction integrity are evaluated within the aggregate boundary.

## 11. Commands

Conceptual commands include Begin Assessment, Record Finding, Modify Finding where permitted by domain semantics, Correct Finding, Complete Assessment, Amend Assessment, and Late Assessment Documentation.

## 12. Correction vs Amendment

Correction addresses an error. Amendment records an allowed subsequent change/clarification. Late documentation concerns an earlier occurrence recorded later. These are distinct semantic operations.

## 13. Encounter Relationship

Assessment remains within the Encounter bounded context and references the Encounter without owning the Encounter lifecycle.

## 14. Post-Encounter

Changes after Encounter completion or closure follow governed Assessment semantics and do not automatically reopen Encounter.

## 15. Offline

Assessment conflicts are evaluated through Assessment meaning and invariant rules. Synchronization transport does not decide whether one finding supersedes another.

## 16. Non-Ownership

Assessment does not own Encounter disposition, triage, medication lifecycle, referral lifecycle, longitudinal condition authority, or final clinical authority.

## 17. Canonical Status

**Approved Architectural Baseline — v0.1.0**
