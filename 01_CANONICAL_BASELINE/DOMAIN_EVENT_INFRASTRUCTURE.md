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
