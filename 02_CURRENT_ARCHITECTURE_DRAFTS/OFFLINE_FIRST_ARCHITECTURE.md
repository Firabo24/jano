# OFFLINE_FIRST_ARCHITECTURE.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Jano Health / Cross-Cutting Architecture

## 1. Purpose

Define offline-first as a cross-cutting operating constraint for Jano Health.

## 2. Principle

Offline-first means clinically useful local operation can continue without constant internet connectivity.

## 3. Conceptual Model

```text
Local Clinical Operation
        ↓
Local Authoritative Domain State
        ↓
Pending Propagation / Sync
        ↓
Later Reconciliation
```

## 4. Cross-Cutting Scope

Offline-first affects clinical domains, identity, authorization, audit, AI availability, integration queues, and synchronization.

## 5. Local vs Global

```text
Accepted Locally ≠ Globally Reconciled
Valid Offline Command ≠ Guaranteed Conflict-Free Command
Local Identity State ≠ Global Identity Truth
```

## 6. Domain Ownership

Each bounded context retains ownership of its meaning. Offline infrastructure must not silently decide clinical meaning.

## 7. Safety

Essential clinical care cannot depend solely on connectivity or AI availability. Unsafe unresolved conflicts must remain explicit.

## 8. Identity

Offline registration may create multiple representations; duplication does not imply multiple persons.

## 9. Auditability

Offline activity must remain attributable and later reconcilable without erasing historical lineage.

## 10. Integration

External integration work may queue while offline; boundary semantics remain owned by the interoperability layer.

## 11. Non-Goals

No concrete sync protocol, conflict algorithm, local database schema, queue technology, or deployment topology is finalized here.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
