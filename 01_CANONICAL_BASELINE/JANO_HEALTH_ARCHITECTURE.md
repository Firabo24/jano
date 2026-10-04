# JANO_HEALTH_ARCHITECTURE.md

**Version:** v0.1.1
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Document Purpose

This is the canonical architectural spine for Jano Health. It defines the top-level architecture, boundaries, principles, ownership rules, dependency semantics, and architectural constraints against which later architecture documents are reconciled.

## 2. Scope

Jano Health is healthcare infrastructure designed to connect patients, healthcare workers, facilities, clinical workflows, clinical intelligence, health data, and interoperability, especially in low-resource and low-connectivity environments.

Anchor is out of scope. Fayda remains external.

## 3. Architectural Goals

- clinical continuity and patient-centered care;
- offline-first operation;
- trustworthy identity and governance;
- bounded clinical domains with explicit ownership;
- governed AI-assisted clinical decision support;
- interoperability by design;
- auditability, security, privacy, and accountability;
- modularity without premature deployment fragmentation.

## 4. Definition of Jano Health

Jano Health is a modular healthcare infrastructure platform rather than only an EHR or AI application.

## 5. Canonical Platform Model

```text
Jano Health
├── Healthcare OS → clinical infrastructure and healthcare operations
├── Jano Core → foundational identity, trust, consent, security foundations, events, platform capabilities
├── AI Platform → clinical intelligence, CDS, orchestration, AI services
├── Data Platform → clinical data, events, analytics, research
└── Interoperability → FHIR/HL7/APIs/external healthcare-system connectivity
```

These are top-level architectural domains/capability areas, not automatically five applications, services, clusters, or deployment units.

## 6. Healthcare OS

Healthcare OS is the umbrella clinical architecture/application layer containing multiple clinical domains and bounded-context candidates.

It owns clinical meaning and authoritative clinical state for the clinical meanings represented by its domains. It is not one giant bounded context.

## 7. Jano Core

Jano Core contains only capabilities that are foundational, cross-domain, independently governed, required by multiple Jano capabilities, and free of clinical business logic.

Its foundational identity boundary includes Person Identity, Patient Relationship, Identity Representations, external identity relationships, and EMPI capability.

## 8. AI Platform

AI is a governed supporting capability. Clinical Decision Support is broader than AI. AI may assist CDS but is not the source of clinical authority.

## 9. Data Platform

Data Platform consumes governed domain data and events for analytics, research, and related data capabilities. It does not become owner of all clinical truth.

## 10. Interoperability

Interoperability is the external integration boundary/capability for FHIR, HL7, APIs, and external healthcare systems. It translates at boundaries without owning internal clinical meaning.

## 11. Dependency Semantics

Structural dependency, runtime interaction, data flow, event flow, and external integration are distinct.

```text
Foundational Capabilities
        ↑
Clinical Domains
        │
        ├── request AI assistance → AI Platform
        ├── publish governed data/events → Data Platform
        └── use integration boundary → Interoperability
```

A runtime interaction is not automatically a structural dependency.

## 12. Bounded Context Principle

```text
Logical Clinical Boundary
        ↓
Modular Implementation
        ↓
Optional Future Service Extraction
```

Bounded contexts are logical boundaries first. Deployment boundaries come later.

## 13. Offline-First Position

Offline-first is a master architectural constraint affecting clinical runtime, identity, authorization, local operation, synchronization, conflict handling, audit, AI availability, and integration continuity as applicable.

Detailed synchronization algorithms remain deferred.

## 14. Security and Trust

Security is cross-cutting. Jano Core provides foundational identity, authorization, consent, and trust capabilities, while detailed security policy and controls remain a dedicated architecture concern.

## 15. MVP Boundary

```text
Patient Registration
        ↓
Identity / EMPI
        ↓
Triage
        ↓
Encounter
        ↓
Clinical Assessment
        ↓
Clinical Decision Support
        ↓
Diagnosis
        ↓
Treatment
        ↓
Medication
        ↓
Referral
        ↓
Follow-up
```

This is an end-to-end clinical care loop, not proof that every step is a separate bounded context.

## 16. Architectural Non-Goals

No detailed database schema, API contract, exact FHIR resources, synchronization algorithm, cloud topology, Kubernetes design, microservice map, exact AI models, prompts, or frontend architecture is established here.

## 17. Core Rules

Clinical domains own clinical meaning. Jano Core provides foundations. AI supports but does not govern clinical truth. Data Platform remains downstream. Interoperability remains an external boundary. Security and offline-first are cross-cutting. Fayda is external. Anchor is separate.

## 18. Final Status

This document remains the canonical master architecture against which subsequent documents are reconciled.
