# Enterprise Architecture Overview

**Document category:** Enterprise Architecture  
**Status:** Draft for Architectural Review  
**Version:** v0.2.0

## Purpose
Provide one coherent architectural entry point linking Jano's platform model, clinical domain boundaries, foundational capabilities, cross-cutting qualities, external integrations, runtime concerns, and governance artifacts.

## Canonical Platform Model

```text
Jano Health
├── Healthcare OS
│   └── Clinical infrastructure and healthcare operations
├── Jano Core
│   └── Foundational identity, consent, authorization, trust, audit, identifiers and event infrastructure
├── AI Platform
│   └── Supporting intelligence, CDS, orchestration, context and governed AI services
├── Data Platform
│   └── Governed data, event, analytics and research capabilities
└── Interoperability
    └── External healthcare-system connectivity, translation and integration boundaries
```

## Dependency Direction

Domain meaning flows upward into governed representations and outward through explicit boundaries. Foundations may support many domains, but foundational components do not acquire clinical business ownership merely because they are used by clinical workflows.

## Cross-Cutting Qualities
Security, privacy, clinical safety, auditability, offline continuity, data quality and operability apply across every logical layer.

## Architecture by Concern

| Concern | Primary owner | Key rule |
|---|---|---|
| Person identity | Jano Core | Internal identity remains authoritative inside Jano |
| Clinical state | Owning clinical domain | No cross-domain direct mutation |
| Clinical intelligence | AI Platform/CDS | Assistive; review and governance required |
| Analytics | Data Platform | Downstream, purpose-governed |
| External exchange | Interoperability | Translation at boundary |
| Event propagation | Event Infrastructure | Infrastructure does not own event meaning |
| Offline continuity | Cross-cutting | Local state has explicit reconciliation semantics |

## Architecture Completeness

Detailed artifacts in this pack provide view-specific authority. No single document should be interpreted as overriding an approved baseline unless a governed architectural change explicitly supersedes it.

## Status
Draft for Architectural Review.
