# JANO_HEALTH_ARCHITECTURE.md

**Version:** v0.1.1
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Document Purpose

This is the canonical architectural spine for Jano Health. It defines the top-level architecture, boundaries, principles, ownership rules, dependency semantics, and architectural constraints against which later architecture documents are reconciled.

## 2. Scope

Jano Health is healthcare infrastructure designed to connect patients, healthcare workers, facilities, clinical workflows, clinical intelligence, health data, and interoperability, especially in low-resource and low-connectivity environments.

Out-of-scope external systems remain outside the Jano architecture. Fayda remains external.

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

Clinical domains own clinical meaning. Jano Core provides foundations. AI supports but does not govern clinical truth. Data Platform remains downstream. Interoperability remains an external boundary. Security and offline-first are cross-cutting. Fayda is external. Out-of-scope external systems remain separate.

## 18. Final Status

This document remains the canonical master architecture against which subsequent documents are reconciled.
## 7. Canonical Platform Semantics

The five top-level areas are logical architectural domains/capability areas. They are not a commitment to five applications, five services, five infrastructure clusters, or a mandatory distributed deployment.

```text
Jano Health
├── Healthcare OS
│   └── Clinical infrastructure and healthcare operations
├── Jano Core
│   └── Foundational identity, trust, consent, authorization foundations,
│       audit/accountability, identifiers, and event infrastructure
├── AI Platform
│   └── Clinical intelligence, CDS support, orchestration, and AI services
├── Data Platform
│   └── Governed clinical data, event data, analytics, reporting, research
└── Interoperability
    └── External healthcare-system connectivity and translation boundaries
```

## 8. Dependency Direction

Structural dependency, runtime interaction, data flow, event flow, and external integration are different architectural relationships.

```text
Foundational capabilities
        ↓
Clinical domains / authoritative clinical state
        ↓
Governed events and data
        ↓
AI / analytics / research / external integration
```

A runtime interaction does not by itself create a structural dependency. A downstream consumer does not become the owner of the upstream domain's meaning.

## 9. Healthcare OS Boundary

Healthcare OS is the clinical infrastructure/application layer. It contains multiple clinical capabilities and bounded-context candidates and defines how clinical workflows traverse them.

Healthcare OS does not own Jano Core identity foundations, the meaning of AI recommendations, Data Platform analytical ownership, or external-system contracts.

Clinical domains inside Healthcare OS own the authoritative meaning and state for the clinical concepts they govern.

## 10. Jano Core Boundary

Jano Core remains intentionally narrow. A capability belongs in Core only when it is:

- foundational;
- cross-domain;
- independently governed;
- required by multiple Jano capabilities; and
- free of clinical business logic.

Core must not become a generic container for everything shared by the platform.

## 11. AI Boundary

AI is supporting intelligence. The architectural relationship remains:

```text
Clinical Context
      ↓
Clinical Decision Support
      ↓
AI Assistance where appropriate
      ↓
Safety / Validation
      ↓
Clinician Review
      ↓
Clinical Action
```

AI does not own clinical truth, identity authority, authorization authority, or final clinical decisions. Core clinical workflows must be able to continue when AI is unavailable.

## 12. Data Boundary

Clinical domains remain authoritative for their own clinical meaning and state. Governed clinical information and domain events may feed Data Platform capabilities for analytics, reporting, research, and other approved secondary uses.

```text
Clinical Domain
      ↓
Authoritative Clinical State
      ↓
Governed Data / Domain Events
      ↓
Data Platform
```

Data Platform is not the universal source of truth for clinical state.

## 13. Interoperability Boundary

Interoperability owns the external boundary: external contracts, translation, adapters, transport, integration policy, and external-system communication. It does not own internal clinical meaning.

```text
Internal Jano Meaning
      ↓
Integration Contract / Translation Boundary
      ↓
Interoperability
      ↓
External System
```

FHIR, HL7, and API details are defined in dedicated documents rather than becoming the internal domain model.

## 14. Identity Boundary

Jano Core owns the authoritative internal identity foundation. This includes Person Identity, Patient Relationship semantics, Workforce/User Identity, Facility/Organization Identity, and External Identity Relationships.

Fayda is an external identity relationship and never replaces the internal Jano identity model.

Identity is not authentication, authorization, consent, or clinical responsibility.

## 15. Clinical Identity Rule

Clinical information must have an explicit identity context before authoritative clinical attribution. Provisional or unresolved identity context must not silently become globally reconciled identity truth.

Identity changes propagate through identity-owned facts/events and domain-owned interpretation/commands. Identity does not directly mutate clinical aggregates.

## 16. Offline-First Position

Offline-first is a master architectural constraint affecting, where applicable, clinical runtime, identity, authorization, local state, audit/accountability, AI availability, interoperability queues, and synchronization.

The essential distinction is:

```text
Local State ≠ Globally Reconciled State
```

Synchronization infrastructure does not decide clinical meaning.

## 17. Security and Trust Boundary

Security, privacy, auditability, trust, and accountability are cross-cutting. Jano Core provides foundational capabilities, but individual domains remain responsible for domain-specific safety and authorization checks.

A trusted operation is not automatically a clinically valid operation.

## 18. Clinical Workflow Boundary

Healthcare OS defines the overall clinical workflow architecture without introducing a universal workflow owner or central workflow engine.

A workflow may cross domains while each domain retains ownership of its authoritative state.

## 19. Initial Clinical Care Loop

The current conceptual MVP care loop is:

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
Diagnosis / Clinical Conclusion
        ↓
Treatment
        ↓
Medication
        ↓
Referral / Care Coordination
        ↓
Follow-up / Continuity
```

This is a workflow, not a statement that every stage is its own bounded context or aggregate.

## 20. Encounter vs Longitudinal State

Encounter represents an individual clinical interaction. Longitudinal conditions, long-term medication meaning, care plans, follow-up, and disease progression can have meaning across multiple encounters.

Those longer-lived boundaries remain subject to dedicated DDD analysis.

## 21. Architectural Maturity Vocabulary

Use these labels consistently:

```text
Approved Architectural Baseline
Strong Candidate
Candidate
Proposed
Open
Deferred
Rejected
```

A complete document is not automatically an approved decision.

## 22. Deployment Philosophy

Logical boundaries precede deployment boundaries. A modular monolith is valid. Future service extraction is optional and evidence-driven.

No cloud provider, orchestrator, broker, service topology, or deployment technology is a mandatory dependency of this master architecture unless a later dedicated decision explicitly establishes one.

## 23. MVP Boundary

The MVP boundary is deliberately narrower than the future platform vision. Existing product evidence concerns a functional product/architecture foundation; deployment scale, national clinical operation, revenue, and broad validation are not implied by the architecture document.

## 24. Future Expansion Boundary

Future areas may include laboratory, radiology, pharmacy, appointments, emergency care, maternal and child health, infectious disease, chronic disease, public health, community health, and other adjacent capabilities. Their final bounded-context status remains evidence-driven.

## 25. Architectural Constraints

- No universal patient aggregate.
- No universal clinical aggregate.
- No universal workflow engine.
- No AI-owned clinical truth.
- No Data-Platform-owned clinical truth.
- No cross-domain direct mutation of clinical aggregates.
- No destructive identity merge by default.
- No assumption that synchronization resolves clinical meaning.
- No assumption that a domain event is the same thing as audit, workflow notification, synchronization record, or integration message.

## 26. Non-Goals

This document does not define database schemas, API contracts, exact FHIR resources, detailed HL7 message structures, exact AI models or prompts, detailed sync algorithms, frontend component architecture, cloud-specific infrastructure, or microservice topology.

## 27. Known Open Questions

- Final clinical bounded-context landscape beyond the approved Encounter context.
- Longitudinal ownership across encounter-oriented workflows.
- Final classification of diagnosis, treatment, follow-up, laboratory, radiology, pharmacy, emergency, and specialty/program boundaries.
- Detailed interoperability contracts.
- Detailed security, privacy, retention, and operational policies.

## 28. Architectural Risks

Primary risks include domain overlap, premature decomposition, unclear ownership, AI authority leakage, identity ambiguity, offline conflict amplification, platform leakage into clinical domains, and specialty/program proliferation.

Mitigation is explicit ownership, maturity labels, domain-owned state, evidence-based DDD analysis, and dedicated architectural review.

## 29. Decision Summary

The current canonical spine is intentionally modular and implementation-neutral: Healthcare OS is the clinical umbrella; Jano Core is narrow and foundational; AI is supporting intelligence; Data Platform is downstream; Interoperability owns external boundaries; offline-first, security, privacy, trust, and auditability are cross-cutting.

## 30. Relationship to Detailed Architecture

Detailed architecture documents refine but do not silently override this master architecture. Any proposed change to an approved canonical decision requires explicit architectural review and versioned change control.

## 31. Canonical Status

**Approved Architectural Baseline — v0.1.1**
