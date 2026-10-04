# Event Lifecycle Architecture

**Document category:** Current Architecture Draft  
**Status:** Draft for Architectural Review  
**Version:** v0.1.1

## Purpose
Separate the lifecycle of an immutable domain fact from the infrastructure lifecycle used to propagate and process that fact.

## Two Different Lifecycles

### 1. Domain Event Semantic Fact
A domain event is a fact that an authoritative domain state change occurred. Its semantic meaning is owned by the originating aggregate/bounded context. The fact is not mutable business state.

### 2. Infrastructure Propagation / Processing Lifecycle
After a domain fact exists, infrastructure may track delivery or processing state, for example pending propagation, delivered, retried, delayed or failed. These are infrastructure handling states and must not be confused with changes to the original business fact.

```text
Authoritative Domain State Change
        ↓
Domain Event (immutable semantic fact)
        ↓
Event Infrastructure Handling
        ├── pending
        ├── delivered
        ├── retry
        └── failed / dead-lettered where governed
        ↓
Consumer Processing / Domain Reaction
        ↓
Receiving Domain-Owned Command or Interpretation
```

## Ordering
Aggregate causal order is meaningful within the owning domain. Global arrival order is not automatically equivalent to domain causal order. Offline reconnection can produce delayed delivery. Consumers must therefore interpret events in the context of the source domain's semantics and their own invariants.

## Corrections
If a business fact must be corrected, the owning domain emits the appropriate new domain meaning according to its correction model. Infrastructure does not edit the prior event fact to make delivery or processing appear different.

## Failure Semantics
Failure to deliver an event does not mean the underlying domain state failed to change. Conversely, successful delivery does not mean the receiving domain has accepted or transformed the fact into local authoritative truth.

## Status
Draft for Architectural Review.
