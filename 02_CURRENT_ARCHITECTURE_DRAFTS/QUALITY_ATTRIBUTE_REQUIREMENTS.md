# QUALITY_ATTRIBUTE_REQUIREMENTS.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Jano Health / Cross-Cutting Quality Architecture

## 1. Purpose

Capture qualitative quality-attribute commitments already established in the architecture and identify quantitative targets that remain deliberately open.

## 2. Availability / Continuity

Clinical continuity is a core goal. Offline-first reduces reliance on continuous network availability. Numeric availability SLOs remain TBD.

## 3. Reliability / Resilience

The architecture emphasizes fault tolerance, recoverability, explicit failure states, offline continuity, and auditable correction. Numeric targets remain TBD.

## 4. Security / Privacy

Security-by-default, privacy-by-design, identity/authorization/consent/trust, and auditability are foundational. Numeric control objectives remain TBD.

## 5. Performance

Performance matters for clinical workflow usability and AI-assisted response. Concrete latency budgets remain TBD and must not be invented here.

## 6. Offline Capability

Critical clinical workflows should continue during connectivity loss. Maximum offline duration is not yet specified.

## 7. Interoperability

FHIR/HL7/APIs and external integration boundaries are architectural requirements. Exact conformance targets remain deferred.

## 8. Maintainability / Modularity

Logical modularity, bounded contexts, domain ownership, and optional future service extraction are required. Deployment decomposition remains open.

## 9. Auditability

Consequential activities require attributable, reviewable history consistent with domain and governance rules.

## 10. Open Quantitative Commitments

Availability SLOs, API latency budgets, sync timing objectives, RPO/RTO, scale thresholds, and accessibility compliance levels require deliberate future decisions.

## 11. Non-Goals

This document does not invent quantitative targets.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
