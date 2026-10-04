# INTEROPERABILITY_ARCHITECTURE.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Jano Health / External Integration Boundary

## 1. Purpose

Define Interoperability as the external integration boundary for Jano Health.

## 2. Scope

FHIR, HL7, APIs, external healthcare systems, facility systems, national/regional systems, and translation between external representations and Jano internal meaning.

## 3. Boundary Model

```text
External System
        ↓
Interoperability Boundary
        ↓
Jano Internal Semantic Model
```

## 4. Ownership

Interoperability owns external contracts, translation, adapters, integration policy, and external communication. It does not own internal clinical meaning.

## 5. FHIR / HL7

FHIR and HL7 are supported interoperability standards where applicable. Exact resource and message specifications are deferred.

## 6. Identity / Fayda

External identity is represented as an external relationship/evidence. Fayda remains external and is not collapsed into the Jano internal identity model.

## 7. Clinical Systems

External labs, radiology, pharmacies, hospital information systems, and national systems connect through explicit integration boundaries.

## 8. Data / Events

Interoperability may consume or publish governed representations, but external representation does not replace internal domain truth.

## 9. Security

External integrations require appropriate identity, authorization, consent, trust, and audit controls.

## 10. Offline

Integration requests/results may be delayed during offline periods; local clinical continuity remains domain-owned.

## 11. Non-Goals

No exact FHIR profiles, HL7 messages, API contracts, adapters, gateway technology, or transport protocol is finalized here.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
