# Architecture Traceability Matrix — Full

**Document category:** Enterprise Architecture  
**Status:** Draft for Architectural Review  
**Version:** v0.2.0

## Purpose
Link major architectural concerns to their owners, controlling artifacts, validation evidence and review state. This matrix is a documentation control artifact, not a substitute for the authoritative documents.

## Traceability

| Concern | Primary authority | Supporting artifacts | Validation / evidence | Status |
|---|---|---|---|---|
| Overall platform boundary | JANO_HEALTH_ARCHITECTURE.md | Enterprise overview, context landscape | architecture review | Approved baseline |
| Clinical infrastructure | HEALTHCARE_OS_ARCHITECTURE.md | Clinical domain architecture | domain review | Approved baseline |
| DDD boundaries | CLINICAL_DDD_ARCHITECTURE.md | BC/aggregate catalogs | aggregate/boundary review | Approved baseline |
| Encounter lifecycle | ENCOUNTER_* baseline set | Runtime and event drafts | state/command/event review | Approved baseline |
| Assessment | ASSESSMENT_AGGREGATE_ARCHITECTURE.md | assessment runtime draft | aggregate evidence | Approved baseline |
| Identity foundations | IDENTITY_ARCHITECTURE.md | patient identity, EMPI | identity review | Approved baseline |
| EMPI | EMPI_ARCHITECTURE.md | EMPI operating model | reconciliation review | Approved baseline |
| Consent | CONSENT_ARCHITECTURE.md | privacy/governance | governance review | Approved baseline |
| Authorization | AUTHORIZATION_FOUNDATIONS_ARCHITECTURE.md | authorization architecture | security review | Approved baseline |
| Trust | TRUST_ARCHITECTURE.md | security/privacy | trust/security review | Approved baseline |
| Audit | AUDIT_ARCHITECTURE.md | audit accountability draft | accountability review | Approved baseline |
| Event infrastructure | DOMAIN_EVENT_INFRASTRUCTURE.md | event lifecycle/engineering | event review | Approved baseline |
| Offline continuity | OFFLINE_FIRST_ARCHITECTURE.md | state/conflict/sync drafts | resilience validation | Draft |
| AI/CDS | AI platform + CDS drafts | governance, context, review | AI/clinical validation | Draft |
| Data platform | Data architecture | quality/research | data governance validation | Draft |
| Interoperability | Interoperability architecture | FHIR/HL7/external boundaries | conformance validation | Draft |
| Infrastructure | Infrastructure/deployment documents | operations | deployment/resilience evidence | Draft |
| Pilot readiness | Pilot/scale documents | validation and operations | field readiness evidence | Draft |

## Requirement Classes

The matrix should be extended during implementation planning to connect product requirements, architecture decisions, validation cases and operational evidence without changing architectural ownership.

## Status
Draft for Architectural Review.
