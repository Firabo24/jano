# DOMAIN_EVENT_INFRASTRUCTURE.md

**Version:** v0.1.0
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture  
**Parent Architecture:** Jano Core

## 1. Purpose

Define the conceptual infrastructure for domain-event propagation without taking ownership of event meaning.

## 2. Core Model

```text
Owning Aggregate
        ↓
Authoritative State Change
        ↓
Domain Event
        ↓
Core Event Infrastructure
        ↓
Authorized Consumers
```

## 3. Event vs Infrastructure

Domain Event carries domain meaning. Event Infrastructure provides publication, propagation, routing, delivery semantics, ordering awareness, duplicate-safe handling, retry/failure, offline/local propagation, cross-boundary event handling, and authorized event access.

## 4. Ordering

```text
Aggregate Causal Order
        ≠
Global Arrival Order
        ≠
Clinical Occurrence Order
```

## 5. Cross-Aggregate Rule

```text
Domain Event → Workflow / Domain Reaction → Command → Aggregate
```

Direct aggregate mutation is prohibited.

## 6. Offline

```text
Local Domain Event
        ↓
Local Event Infrastructure / Pending Propagation
        ↓
Later Sync
        ↓
Remote Consumer
```

Local event is not automatically global truth.

## 7. Audit

Domain Event is not the same as an Audit Record, though events may contribute to audit evidence.
## 6. Infrastructure Responsibilities

Core Event Infrastructure provides, conceptually:

- publication support;
- propagation;
- routing/delivery;
- authorized event access;
- duplicate-safe delivery handling;
- retry and failure handling;
- local/offline propagation;
- consumer isolation;
- monitoring of infrastructure handling.

## 7. Domain Ownership

The bounded context/aggregate that owns the state change owns the event meaning. Infrastructure does not author or redefine business facts.

## 8. Event Lifecycle vs Event Meaning

```text
Domain Event
    = immutable semantic fact

Infrastructure lifecycle
    = pending / propagating / delivered / retried / failed, as applicable
```

Infrastructure handling state must never be mistaken for mutable domain business state.

## 9. Ordering

```text
Aggregate Causal Order
      ≠
Global Arrival Order
      ≠
Clinical Occurrence Order
```

Consumers must not derive clinical meaning solely from transport order.

## 10. Delivery Failure

A delivery failure does not mean the underlying domain event did not occur. Transport retry state belongs to infrastructure handling.

## 11. Offline Propagation

Local event production can occur without connectivity where the domain supports it. Later propagation does not transfer ownership of the original fact.

## 12. Authorized Consumption

Consumers may access events according to their governed authorization and domain purpose. Broad event visibility is not assumed.

## 13. Cross-Aggregate Coordination

```text
Domain Event
    ↓
Workflow / Domain Reaction
    ↓
Command
    ↓
Receiving Aggregate
```

Direct state mutation across aggregates is not provided by the event infrastructure.

## 14. Duplicate Handling

Infrastructure may prevent duplicate processing/delivery effects where appropriate, but domain semantics remain responsible for deciding whether repeated facts are clinically meaningful.

## 15. Event vs Audit

Infrastructure may support delivery of both, but a domain event and an audit representation are not interchangeable artifacts.

## 16. Implementation Neutrality

No broker, queue, streaming platform, database, cloud vendor, container platform, or service topology is mandated by this architecture.

## 17. Canonical Status

**Approved Architectural Baseline — v0.1.0**
