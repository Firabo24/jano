# ARCHITECTURE_TRACEABILITY_MATRIX.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Jano Health Master Architecture

## 1. Purpose

Provide a conceptual traceability matrix linking major requirements/decisions to architectural owners without introducing implementation contracts.

## 2. Traceability Matrix

| Concern | Primary architectural owner | Supporting boundaries | Status |
|---|---|---|---|
| Person identity | Jano Core Identity | EMPI, Fayda relationship | Decided |
| Encounter lifecycle | Encounter Aggregate | Assessment, CDS, workflow | Decided |
| Assessment findings | Assessment Aggregate | Encounter | Decided baseline |
| Authorization | Jano Core Authorization | Security | Decided |
| Consent | Jano Core Consent | Clinical/Data/AI | Decided |
| Trust | Jano Core Trust | Security | Decided |
| Domain event meaning | Owning domain | Core Event Infrastructure | Decided |
| Event propagation | Core Event Infrastructure | Domains | Decided |
| CDS | Healthcare OS / Clinical capability | AI Platform | Decided direction |
| AI assistance | AI Platform | CDS / Clinical domains | Decided |
| Analytics/research | Data Platform | Governed domain data | Decided |
| External healthcare integration | Interoperability | Clinical/Data/Identity | Decided direction |
| Offline operation | Cross-cutting | All applicable domains | Decided |

## 3. Decision Traceability

Architecture decisions should point back to the authoritative document that establishes their meaning, and later implementations should not silently contradict these boundaries.

## 4. Open Traceability

Final clinical bounded contexts, detailed sync behavior, exact security controls, detailed interoperability contracts, and quantitative quality targets remain open/deferred.

## 5. Non-Goals

No code-to-requirement matrix, schema traceability, API traceability, or vendor-specific trace is defined here.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
