# ENCOUNTER_DOMAIN_EVENT_ARCHITECTURE.md

**Version:** v0.1.1
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Event Principle

An Encounter domain event is a fact that an authoritative Encounter state change occurred.

## 2. Ownership

Encounter owns the semantic meaning of Encounter events. Core Event Infrastructure provides propagation and delivery capabilities only.

## 3. Conceptual Flow

```text
Encounter Aggregate
        ↓
Authoritative State Change
        ↓
Encounter Domain Event
        ↓
Event Infrastructure
        ↓
Authorized Consumers
```

## 4. Causality

Aggregate causal order is not the same as global arrival order, and neither is identical to clinical occurrence order.

## 5. Cross-Aggregate Reaction

```text
Domain Event
    ↓
Workflow / Domain Reaction
    ↓
Command
    ↓
Receiving Aggregate
```

## 6. Offline

Local event creation does not automatically mean global reconciliation. Duplicate delivery does not imply duplicate clinical occurrence.
