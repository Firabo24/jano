# ENCOUNTER_AGGREGATE_FINALIZATION.md

**Version:** v0.1.0
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Finalization Principle

Completion establishes that required encounter work has been completed. Closure establishes a stronger historical/accountability boundary.

## 2. Completion

Completion belongs to the Encounter Aggregate and remains distinct from closure.

## 3. Closure

Closure belongs to the Encounter Aggregate and protects the historical/accountability boundary.

## 4. Post-Closure

Post-closure correction, amendment, late documentation, new clinical information, and reopening are not interchangeable.

## 5. Integrity

Historical identity and clinical chronology must be preserved. Later changes must remain explainable rather than silently rewriting history.

## 6. Cross-Aggregate Rule

Another aggregate must not directly mutate finalization state.
## 7. Completion

Completion is a domain state boundary indicating that the Encounter's clinical work has reached its completion semantics. Completion is not the same as archival or irreversible closure.

## 8. Closure

Closure is the stronger historical/accountability boundary. It protects the interpretation that the Encounter's active lifecycle is over, while still allowing explicitly governed post-closure correction or amendment operations.

## 9. Preconditions

Completion/closure must respect the Encounter Aggregate's invariant family, identity context, patient association, attribution, lifecycle, temporal scope, and applicable domain safety rules.

No universal rule is imposed that every secondary clinical workflow must be complete before closure unless separately justified by the domain.

## 10. Post-Closure Change

```text
Correction ≠ Reopening
Amendment ≠ New Encounter
Late Documentation ≠ Reopening
New Clinical Information ≠ Historical Rewrite
```

## 11. Historical Integrity

The architecture preserves original authorship, relevant temporal semantics, and the fact that a correction or amendment occurred later.

## 12. Cross-Aggregate Effects

Assessment, Medication, Referral, and other domain lifecycles do not become Encounter state merely because they are coordinated during or after Encounter finalization.

## 13. Offline Finalization

A local completion/closure transition is a valid local state transition only when local domain rules permit it. Global reconciliation is a subsequent infrastructure concern.

## 14. Canonical Status

**Approved Architectural Baseline — v0.1.0**
