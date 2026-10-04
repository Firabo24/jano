# AUDIT_ARCHITECTURE.md

**Version:** v0.1.0  
**Status:** Approved Architectural Baseline  
**Document Owner:** Jano Health Architecture  
**Parent Architecture:** Jano Core

## 1. Purpose

This document defines the authoritative architectural position for audit and accountability within Jano Health. Audit provides a meaningful representation of consequential activity and accountability context. It is not a generic log of every technical operation.

## 2. Architectural Boundary

Jano Core owns foundational audit/accountability meaning. Clinical and platform domains remain owners of their own business state and may produce audit representations when activity is materially consequential, governed, or required for accountability.

```text
Actor / Authorized Context
        │
        ▼
Governed Operation or Material State Change
        │
        ▼
Audit / Accountability Representation
        │
        ├── actor
        ├── subject / resource
        ├── action / operation
        ├── context
        ├── time
        ├── outcome
        ├── governance context
        └── accountability relationship
```

## 3. Critical Distinctions

```text
Audit Record        ≠ Domain Event
Audit               ≠ Identity
Audit               ≠ Authentication
Audit               ≠ Authorization
Audit               ≠ Consent
Audit               ≠ Clinical State
Audit               ≠ Technical Telemetry
```

A domain event expresses a domain-owned fact of state change. An audit record expresses accountability information about consequential activity. A technical log may exist for diagnostics without becoming an audit record.

## 4. Ownership and Authority

Jano Core owns the foundational audit/accountability meaning and cross-domain accountability foundations. The underlying business state remains owned by the domain that owns that meaning. Audit does not become a second source of clinical truth.

## 5. What Audit Represents

Where governed by policy, audit may represent:

- identity changes and reconciliation actions;
- authorization-sensitive operations;
- consent or governance decisions;
- material clinical actions;
- significant corrections, amendments, or reversals;
- security-sensitive activity;
- other consequential operations defined by governance.

The representation preserves original actor/accountability provenance. Later correction of an underlying domain record must not silently erase the historical fact that an earlier action occurred.

## 6. Offline Accountability

Offline operation does not remove the need for accountability. A locally accepted audit representation may exist before global synchronization.

```text
Local Accountability
        ≠
Globally Reconciled Accountability
```

Synchronization may reconcile delivery or representation state, but it must not rewrite the original accountability relationship.

## 7. Security and Privacy

Audit information is itself sensitive. Access to audit information must be governed separately from ordinary clinical viewing where appropriate. Detailed security controls, retention periods, encryption implementation, SIEM integration, and storage technology remain outside this baseline and belong to later security/operations documents.

## 8. Domain Interaction

```text
Domain-owned state change
        ↓
Domain event / governed fact where applicable
        ├──────────────► other authorized domain reactions
        └──────────────► audit representation where required
```

Audit is an accountability representation, not an instruction to mutate domain state.

## 9. Non-Responsibilities

Audit does not own:

- clinical state;
- identity equivalence decisions;
- authentication decisions;
- authorization policy as a whole;
- consent meaning;
- synchronization conflict resolution;
- AI clinical authority;
- analytics ownership;
- infrastructure telemetry as a substitute for accountability.

## 10. Deferred Design

The following remain deferred to dedicated documents: storage architecture, retention schedules, immutable-storage mechanisms, query/reporting implementation, SIEM/security tooling, legal retention obligations, export formats, and operational recovery procedures.

## 11. Approval Constraints

This baseline does not authorize unlimited audit capture. The set of auditable actions, retention, access, redaction, and disclosure must be established through explicit governance and security work.

## 12. Change History

| Version | Change | Status |
|---|---|---|
| v0.1.0 | Canonical audit/accountability baseline restored to the pack. | Approved Architectural Baseline |
