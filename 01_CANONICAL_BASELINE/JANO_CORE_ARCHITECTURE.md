# JANO_CORE_ARCHITECTURE.md

**Version:** v0.1.0
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Purpose

Jano Core contains foundational capabilities required across Jano Health.

## 2. Inclusion Test

A capability belongs in Jano Core only when it is foundational, cross-domain, independently governed, required by multiple capabilities, and free of clinical business logic.

## 3. Core Structure

```text
Jano Core
├── Identity Foundations
├── Consent
├── Authorization Foundations
├── Trust Foundations
├── Audit / Accountability Foundations
├── Foundational Identifiers / References
└── Event Infrastructure Foundations
```

## 4. Identity Authority

Jano Core is the authoritative internal identity foundation. Patient Identity and EMPI operate inside this boundary.

## 5. Boundaries

Core does not own Encounter, Assessment, Treatment, Medication, Referral, clinical workflows, CDS recommendations, analytics/research ownership, or external interoperability semantics.

## 6. Events

Core provides event infrastructure. Domain contexts own the meaning of their domain events.

## 7. Security

Security is cross-cutting. Core provides foundational primitives but does not absorb all detailed security policy.

## 8. Offline

Offline-first applies across Core capabilities, but detailed synchronization mechanics remain deferred.
