# Architecture Principles

**Document category:** Enterprise Architecture  
**Status:** Draft for Architectural Review  
**Version:** v0.2.0

## Purpose
Define the principles that constrain all Jano Health architecture documents and prevent local design choices from silently changing the platform's canonical architecture.

## Principles

| Principle | Architectural consequence |
|---|---|
| Healthcare infrastructure first | Jano is a platform for clinical continuity, not a feature wrapper around one workflow. |
| Clear ownership | Authoritative meaning remains with the domain that owns it. |
| Foundational Core stays narrow | Jano Core contains only foundational, cross-domain, independently governed capabilities without clinical business logic. |
| Clinical authority stays clinical | AI, data, interoperability and infrastructure may support clinical work but do not become clinical authorities. |
| Identity before attribution | Clinical data is not attributed without explicit identity context. |
| Match is not truth | EMPI evaluation and candidate relationships do not automatically become confirmed identity equivalence. |
| Coordination over mutation | Cross-boundary coordination uses events/workflows/commands rather than direct foreign aggregate mutation. |
| Offline by design | Local operation must have explicit semantics; local acceptance is not global reconciliation. |
| Safety across boundaries | Clinical safety and fail-safe behavior remain cross-cutting requirements. |
| Provider neutrality | Cloud/infrastructure choices may realize the architecture but are not the architecture itself. |
| Logical before deployment | Modular boundaries are defined before deployment/service topology. |
| Evidence before promotion | A draft becomes baseline only through explicit review and evidence. |

## Non-Principles

The following are not mandatory architectural principles: one aggregate per noun, mandatory microservices, a specific cloud provider, a specific database, a particular API framework, autonomous AI clinical mutation, or a single universal patient/workflow aggregate.

## Architecture Review Test
Every material proposal should identify the owner, authoritative state, invariants, lifecycle, cross-boundary effects, offline implications, security/privacy implications, and evidence required for approval.

## Status
Draft for Architectural Review.
