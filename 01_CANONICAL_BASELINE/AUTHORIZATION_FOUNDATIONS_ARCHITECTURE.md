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
