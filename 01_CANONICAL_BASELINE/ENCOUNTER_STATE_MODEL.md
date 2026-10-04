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
