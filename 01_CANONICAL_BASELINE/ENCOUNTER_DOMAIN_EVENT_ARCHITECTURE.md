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
## 7. Event Meaning

An Encounter Domain Event is an immutable semantic fact that an authoritative Encounter state change occurred.

## 8. Ownership Rule

The Encounter bounded context and aggregate that own the relevant state own the semantic meaning of the event. Jano Core Event Infrastructure does not become the owner of Encounter event meaning.

## 9. Event Categories

Conceptual Encounter event categories follow the approved lifecycle and business meaning, such as establishment, lifecycle transition, triage result change where appropriate, completion, closure, correction, and amendment.

Event naming must express a fact that occurred, not a future intention or workflow request.

## 10. Event vs Other Messages

```text
Domain Event ≠ Workflow Notification
Domain Event ≠ Synchronization Record
Domain Event ≠ Integration Message
Domain Event ≠ Audit Record
```

## 11. Consumers

Consumers may include other clinical domains, AI assistance, analytics, interoperability, synchronization infrastructure, or accountability systems where explicitly governed. Consumption does not transfer ownership.

## 12. Ordering

Aggregate causal order, global arrival order, and clinical occurrence order are distinct.

## 13. Offline

Domain events produced locally remain semantically owned by the producing domain. Propagation status does not mutate the event's business meaning.

## 14. Correction

Correction and amendment can generate additional events that preserve historical lineage rather than mutating an old event into a different business fact.

## 15. Canonical Status

**Approved Architectural Baseline — v0.1.1**
