# HEALTHCARE_OS_ARCHITECTURE.md

**Version:** v0.1.1
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Purpose

Define Healthcare OS as the umbrella clinical architecture for Jano Health.

## 2. Boundary

Healthcare OS contains multiple clinical domains/capabilities and their workflows. It does not become one giant clinical bounded context.

## 3. Conceptual Model

```text
Healthcare OS
│
├── Clinical Domains / Bounded-Context Candidates
├── Clinical Capabilities
├── Clinical Workflows
└── Clinical State
        │
        └── Owned by Relevant Clinical Domains
```

## 4. Domain / Capability / Workflow / Bounded Context

A Clinical Domain is a coherent area of healthcare meaning and responsibility.

A Clinical Capability is something Healthcare OS can do.

A Clinical Workflow is a sequence of clinical activities.

A Bounded Context is a semantic and ownership boundary within which meaning remains consistent.

A workflow can cross bounded contexts. A capability does not automatically equal a bounded context. A bounded context does not automatically equal a microservice.

## 5. Clinical Ownership

Clinical domains own authoritative clinical meaning and state for their meaning. Healthcare OS is the umbrella architecture, not the owner of every individual clinical state.

## 6. MVP

The MVP follows the previously established patient-centered clinical care loop from registration and identity through encounter, assessment, CDS, diagnosis, treatment, medication, referral, and follow-up.

## 7. Clinical Decision Support

CDS is a clinical/workflow capability broader than AI. It may use guidelines, rules, calculations, alerts, or AI assistance. AI remains optional supporting intelligence.

## 8. Offline-First

Offline-first is cross-cutting across Healthcare OS. Clinical workflows must be able to continue when connectivity is unavailable, slow, intermittent, or unreliable, with detailed sync architecture deferred.

## 9. Future Expansion

Future capabilities such as laboratory, radiology, pharmacy, emergency, public health, maternal health, and community health remain separate domain/capability candidates where appropriate. Their exact bounded contexts require later DDD analysis.

## 10. Architectural Rules

- do not centralize clinical meaning in a workflow layer;
- do not make AI a mandatory prerequisite for care;
- do not turn every workflow stage into a domain;
- do not turn every capability into a bounded context;
- do not turn every bounded context into a microservice;
- preserve Anchor separation and Fayda externality.
