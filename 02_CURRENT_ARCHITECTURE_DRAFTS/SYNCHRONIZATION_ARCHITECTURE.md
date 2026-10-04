# SYNCHRONIZATION_ARCHITECTURE.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Jano Health / Offline-First / Domain Event Infrastructure

## 1. Purpose

Define conceptual synchronization semantics for distributed Jano nodes without prescribing implementation algorithms.

## 2. Boundary

Synchronization moves state/evidence/events between local and connected environments while preserving domain ownership.

## 3. Core Model

```text
Local State / Event
        ↓
Valid Domain Transition
        ↓
Synchronization
        ↓
Conflict Detection
        ↓
Domain Interpretation
```

## 4. Conflict Distinction

State Conflict is not the same as Data Replication Conflict. The meaning of a conflict is interpreted by the owning domain.

## 5. No Generic Clinical Merge

Generic merge behavior must never silently determine clinical meaning.

## 6. Identity Synchronization

Identity synchronization may create candidates or unresolved states. Only governed reconciliation establishes authoritative identity relationships.

## 7. Cross-Aggregate Synchronization

Synchronized state changes do not permit direct aggregate mutation. Receiving aggregates remain responsible for their own commands and invariants.

## 8. Event Semantics

Local domain events may be propagated later. Same event delivered twice does not imply two clinical events occurred.

## 9. Ordering

Aggregate causal order, delivery order, and clinical occurrence time remain distinct.

## 10. Safety and Review

Some conflicts require human/domain review and must not be automatically resolved when clinical meaning is uncertain.

## 11. Non-Goals

No specific sync algorithm, conflict-resolution formula, message protocol, database schema, broker, or transport is finalized here.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
