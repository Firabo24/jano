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
## 8. Core Aggregate Invariant Family

The Encounter Aggregate protects:

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
Core Participation / Accountability
+
Reason / Context
+
Current MVP Triage
+
Disposition
+
Completion
+
Closure
```

These concepts form the current approved primary consistency boundary.

## 9. Participant / Accountability

```text
Participant Relationship + Role + Responsibility + Encounter Accountability
```

These relationships are Encounter-specific. The actor's own identity remains owned outside the aggregate.

## 10. Reason / Context

```text
Encounter Initiation Meaning + Reason + Classification
```

Reason is not diagnosis. Its meaning is tied to the Encounter entry context.

## 11. Triage

Current MVP triage is retained inside the primary aggregate because the triage result, encounter entry state, and lifecycle position form one care-entry consistency interpretation.

## 12. Assessment

Assessment remains the approved secondary aggregate baseline within the Encounter bounded context. It is not an independent bounded context.

## 13. Candidate Clinical Conclusion and Treatment

Clinical Conclusion and Treatment remain candidate classifications requiring evidence. Safety or lifecycle characteristics alone are not sufficient proof of separate aggregate ownership.

## 14. State and Command Rule

```text
Actor
  ↓
Command
  ↓
Preconditions
  ↓
Aggregate Invariants
  ↓
State Transition
  ↓
Domain Event
```

## 15. Post-Completion / Post-Closure

Historical correction, amendment, late documentation, new information, and reopening are distinct operations. They must not be collapsed into an undifferentiated state transition.

## 16. Offline Conflict Rule

A valid offline command is not guaranteed to remain globally conflict-free. Conflict interpretation must respect the aggregate's clinical semantics.

## 17. Boundary Falsifiability

Evidence that could justify further separation includes independent invariant coupling, demonstrably independent lifecycle semantics, materially different concurrency behavior, correction requirements, and domain-specific offline conflict behavior.

Evidence that could collapse a candidate includes proof that the state can safely remain coordinated without weakening domain correctness.

## 18. Canonical Status

**Approved Architectural Baseline — v0.1.2**
