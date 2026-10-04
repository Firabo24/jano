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
- preserve external-system separation and Fayda externality.
## 7. Clinical Capability Landscape

The initial landscape contains capabilities and workflow stages that must not be confused with bounded contexts.

| Concept | Current architectural reading |
|---|---|
| Registration | Clinical/administrative capability; identity boundary interaction |
| Identity / EMPI | Foundational platform interaction; not clinical state |
| Triage | Clinical workflow capability; current MVP result remains Encounter-owned |
| Encounter | Approved bounded context and primary aggregate boundary |
| Assessment | Approved secondary aggregate baseline within Encounter context |
| Diagnosis / clinical conclusion | Candidate classification requiring continued evidence where separately modeled |
| Treatment | Candidate classification requiring evidence; medication-specific lifecycle remains separate |
| Medication | Clinical domain/capability with its own lifecycle outside Encounter |
| Referral | Care-coordination domain/capability with its own lifecycle |
| Follow-up | Continuity capability/workflow; final boundary remains open |

## 8. Clinical Domains vs Programs vs Specialties

A chronic-disease program, maternal-health program, specialty service, or public-health initiative does not automatically constitute a bounded context. The deciding factors remain semantic ownership, authoritative state, invariants, lifecycle, correction behavior, concurrency, and offline behavior.

## 9. Workflow Architecture

Healthcare OS defines cross-domain workflow architecture.

```text
Healthcare OS
      ↓
Clinical Workflow Architecture
      ↓
Multiple Domain Activities
      ↓
Domain-Owned Commands / State Changes
      ↓
Domain Events
```

There is no universal clinical workflow engine implied here.

## 10. Clinical Ownership

Each clinical domain owns the meaning and authoritative state for the concepts within its boundary. Healthcare OS owns the umbrella clinical architecture and workflow relationships, not every clinical record or transition.

## 11. Encounter Boundary

Encounter is an individual clinical interaction. It is not a universal episode, longitudinal patient aggregate, or substitute for referral, medication, or long-term condition state.

## 12. Assessment Boundary

Assessment is a secondary aggregate within the Encounter bounded context because its lifecycle, findings, attribution, clinical meaning, and correction/amendment integrity form a separately analyzable consistency boundary. The aggregate's separate status remains governed by its approved baseline.

## 13. Diagnosis and Treatment Maturity

Clinical Conclusion and Treatment remain candidates where the evidence has not been independently finalized. Their concepts must not be separated merely for symmetry, because of safety sensitivity alone, or because they are convenient domain nouns.

## 14. Longitudinal State

Longitudinal conditions, care plans, ongoing treatment, follow-up, and disease progression are not automatically Encounter-owned. Their final ownership requires explicit DDD analysis.

## 15. Cross-Cutting Concerns

Security, privacy, identity, consent, authorization, trust, auditability, offline-first operation, synchronization, and AI assistance cross the clinical architecture without becoming the clinical owner of all state.

## 16. Clinical Safety

Safety requirements belong to the relevant clinical workflow and domain. AI can support CDS but cannot become the clinical authority.

## 17. Offline Clinical Operation

Clinical domains must preserve safe local continuity where designed for offline use. Local acceptance is not equivalent to global reconciliation.

## 18. Interoperability Relationship

External laboratory, radiology, pharmacy, and other systems connect through the Interoperability boundary. External representations are not allowed to replace internal clinical meaning.

## 19. Future Domain Assessment Test

Before promoting a capability to a bounded context, evaluate:

- distinct clinical meaning;
- clear owner;
- authoritative state;
- lifecycle;
- invariants;
- correction/amendment;
- concurrency;
- offline behavior;
- domain event needs;
- coordination cost.

## 20. Quality Gate

A clinical architecture document is not approved merely because a capability exists in the product. Architecture approval requires explicit review of the boundary and its evidence.

## 21. Relationship to DDD

Healthcare OS is the umbrella from which dedicated DDD analysis proceeds. The approved Clinical DDD architecture governs the method of deciding bounded contexts and aggregates.

## 22. Canonical Status

**Approved Architectural Baseline — v0.1.1**
