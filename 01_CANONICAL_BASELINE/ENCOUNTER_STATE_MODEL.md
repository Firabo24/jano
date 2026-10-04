# ENCOUNTER_STATE_MODEL.md

**Version:** v0.1.1
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. State Semantics

```text
Aggregate State
    ≠
Workflow State
    ≠
UI State
    ≠
Persistence State
    ≠
Synchronization State
```

The state model describes authoritative domain state.

## 2. Core Lifecycle

The model distinguishes initiation, active work, completion, closure, cancellation where meaningful, and constrained post-completion/post-closure activities.

Completion and closure are separate boundaries.

## 3. Transition Semantics

```text
Actor
  ↓
Command
  ↓
Preconditions
  ↓
State Transition
  ↓
Invariants
  ↓
Domain Event
```

Command is a request; Domain Event is a fact.

## 4. Post-Completion / Post-Closure

Historical correction, amendment, late documentation, new clinical information, reopening, and a new encounter are distinct semantic cases.

## 5. Cross-Aggregate Interaction

Secondary aggregate changes are coordinated rather than direct mutations.

## 6. Offline and Temporal Semantics

Offline state must be interpreted in domain context. Occurred At, Recorded At, Effective At, Corrected At, and Amended At are distinct conceptual times.
## 8. Canonical State Layers

The model must keep separate:

```text
Domain Aggregate State
Workflow Interpretation
UI State
Persistence State
Synchronization State
```

Only the domain aggregate state determines authoritative clinical meaning.

## 9. Encounter Lifecycle

The approved conceptual lifecycle distinguishes initiation/active work, completion, closure, and controlled cancellation where applicable. Create Encounter is not identical to Start Encounter when the distinction is meaningful in the domain, but creation establishes a valid patient association and an initial valid lifecycle position rather than a pending/unassociated state.

## 10. Command-to-State Rule

```text
Actor
  ↓
Domain Command
  ↓
Validation / Preconditions
  ↓
Invariant Evaluation
  ↓
State Transition
  ↓
Domain Event
```

A command is a request for change. An event is a fact that the change occurred.

## 11. Completion vs Closure

Completion indicates the clinical work has reached completion semantics. Closure is a stronger historical/accountability boundary. Closure does not mean no future amendment is ever possible.

## 12. Post-Completion Documentation

Late documentation and amendment may occur under constrained rules without silently rewriting historical chronology. A new clinical event does not automatically reopen the closed Encounter.

## 13. Temporal Semantics

The architecture distinguishes:

```text
Occurred At
Recorded At
Effective At
Corrected At
Amended At
```

These concepts preserve clinical chronology and accountability rather than acting as interchangeable timestamps.

## 14. Offline State

```text
Local State
    ↓
Valid Local Domain Transition
    ↓
Synchronization
    ↓
Conflict Detection
    ↓
Domain Interpretation
```

Replication conflict and clinical state conflict are different problems.

## 15. Secondary Aggregate State

Assessment uses:

```text
Not Started → Documenting → Completed
```

No Assessment Closed state is implied by the current baseline.

## 16. State Invariant Checks

Every transition must be analyzed against identity, patient association, lifecycle, status, temporal scope, completion/closure, and any relevant aggregate-specific invariants.

## 17. Prohibited Shortcuts

The state model must not infer clinical meaning from synchronization arrival order, UI state, database presence, or event delivery state.

## 18. Canonical Status

**Approved Architectural Baseline — v0.1.1**
