# AUTHORIZATION_FOUNDATIONS_ARCHITECTURE.md

**Version:** v0.1.0
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture  
**Parent Architecture:** Jano Core

## 1. Purpose

Authorization determines whether an actor in a defined context is permitted to request or perform an operation against a resource/domain context.

## 2. Distinctions

```text
Authentication ≠ Authorization
Consent ≠ Authorization
Authorization ≠ Clinical Responsibility
Authorization ≠ Clinical Decision
```

## 3. Conceptual Scope

Core authorization foundations include actor reference, role/category relationship, organizational context, authorization relationship, scope/context, permitted-operation meaning, authorization status, validity/temporal meaning, and history.

## 4. Lifecycle

```text
Established → Active → Revoked / Expired
```

## 5. Domain Interaction

```text
Core Authorization
        ↓
Actor Permitted to Request Operation
        ↓
Clinical Aggregate Evaluates Domain Invariants
```

Authorization does not itself authorize a domain state transition if domain invariants are violated.

## 6. Offline

Offline authorization state is not assumed globally reconciled authorization truth.

## 7. Non-Goals

No final RBAC/ABAC/ReBAC model, policy engine, API, database, or synchronization algorithm is finalized here.
## 7. Authorization Decision Context

Authorization is contextual. A conceptual decision may consider actor identity, organizational/facility context, operation, resource/domain context, applicable authorization relationships, time, and governance constraints.

## 8. Authorization Is Not Clinical Validation

```text
Authorization
      ≠
Clinical Validity
```

A permitted actor can still issue an invalid clinical command. The receiving clinical domain remains responsible for domain invariants and safety rules.

## 9. Authorization Models

This foundation does not mandate a single detailed policy model such as RBAC, ABAC, or ReBAC. Detailed policy architecture is separate and may evolve while preserving the foundational boundary.

## 10. Lifecycle

```text
Established → Active → Revoked / Expired
```

Where an authorization relationship is time-scoped or condition-scoped, its applicability must be evaluated in context.

## 11. Offline

Offline authorization may rely on locally available governed state, but stale local state must not be represented as globally reconciled authorization truth.

## 12. Cross-Facility Boundary

Facility or organizational context is part of authorization context where applicable. Authorization must not silently cross a facility boundary merely because an actor is otherwise authenticated.

## 13. Audit

Material authorization decisions or changes may generate accountability representations. Audit does not replace authorization evaluation.

## 14. Trust

Authorization contributes to trust context but is not itself trust.

## 15. Non-Goals

No concrete policy engine, token format, API contract, database schema, or runtime enforcement implementation is mandated here.

## 16. Canonical Status

**Approved Architectural Baseline — v0.1.0**
