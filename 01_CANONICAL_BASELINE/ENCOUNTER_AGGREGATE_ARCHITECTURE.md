# ENCOUNTER_AGGREGATE_ARCHITECTURE.md

**Version:** v0.1.2
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Primary Aggregate

Encounter Aggregate remains the primary aggregate.

Protected invariant family:

```text
Encounter Identity
+
Patient Association
+
Lifecycle
+
Status
+
Temporal Scope
+
Completion
+
Closure
```

## 2. Aggregate Maturity

Encounter is Primary. Assessment is a Strong Aggregate Candidate. Clinical Conclusion and Treatment remain provisional candidates. Participant, Reason, MVP Triage, Disposition, Completion, and Closure remain inside the Primary Aggregate.

## 3. Assessment

Assessment has its own invariant family and independent correction/amendment semantics sufficient to remain a strong separate candidate, subject to continued validation.

## 4. Clinical Conclusion / Treatment

These remain provisional. Safety sensitivity alone or lifecycle independence alone does not prove aggregate separation.

## 5. Convenience Rule

State must not be included in an aggregate merely because it is displayed, created, or used together. Convenient co-location is not aggregate evidence.

## 6. Cross-Aggregate Coordination

```text
Aggregate A
    ↓
Domain Event
    ↓
Workflow / Domain Reaction
    ↓
Command
    ↓
Aggregate B
```

Direct mutation is prohibited.

## 7. Offline

Aggregate-local state conflict must remain distinct from replication conflict. Generic merge behavior must never silently determine clinical meaning.

## 8. Rejected Extremes

One Giant Aggregate and One Aggregate Per Noun remain rejected.
