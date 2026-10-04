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
## 8. Core Boundary Test

Jano Core is not a generic shared-services bucket. A proposed capability must satisfy all of the following before being placed here:

```text
Foundational
+ Cross-Domain
+ Independently Governed
+ Required by Multiple Capabilities
+ Free of Clinical Business Logic
```

## 9. Core Components

### Identity Foundations
Authoritative internal person/patient identity, workforce/user identity, facility/organization identity, and external identity relationships.

### Consent Foundations
Foundational governance meaning for permitted or constrained use, disclosure, processing, purpose, scope, actor/context, and temporal applicability.

### Authorization Foundations
Foundational permission/context relationships that support access decisions without replacing domain-specific clinical validation.

### Trust Foundations
Contextual trust semantics derived from identity, authentication, authorization, governance, accountability, and operating context.

### Audit / Accountability Foundations
Meaningful accountability representations for materially consequential operations; not a generic technical telemetry stream.

### Foundational Identifiers / References
Identity and reference concepts needed across domains where their meaning is genuinely foundational.

### Event Infrastructure Foundations
Publication, propagation, delivery, retry/failure, authorized consumption, and local/offline propagation capabilities. Event meaning remains domain-owned.

## 10. Core Non-Ownership

Core does not own Encounter state, Assessment state, Medication lifecycle, Referral lifecycle, clinical conclusions, treatment actions, CDS recommendations, Data Platform analytical truth, or Interoperability external semantics.

## 11. Cross-Cutting Security

Security is cross-cutting. Core may host foundational security primitives, but detailed policies remain governed across the platform and within relevant domains.

## 12. Offline

Core capabilities must respect disconnected operation without redefining domain meaning. Local identity, authorization, consent, audit, and event states are not automatically globally reconciled.

## 13. Architectural Risk

The primary Core risk is scope expansion. Any proposal that is merely convenient to share, rather than genuinely foundational, should remain outside Core.

## 14. Relationship to Other Domains

Core is upstream/foundational in structure while AI, Data, Interoperability, and clinical domains remain consumers or interacting contexts according to their own boundaries.

## 15. Canonical Status

**Approved Architectural Baseline — v0.1.0**
