# AUDIT_ACCOUNTABILITY_ARCHITECTURE.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Jano Core / Security / Cross-Cutting Governance

## 1. Purpose

Define audit and accountability as a cross-cutting foundation for trustworthy healthcare operations.

## 2. Accountability Model

```text
Actor Identity
 +
Authorization / Consent / Trust Context
 +
Action / State Change
 +
Time / Provenance
 =
Accountable Activity
```

## 3. Domain Audit vs Domain Event

A Domain Event records a domain state change. An Audit Record records accountability/evidence. They may be related but are not identical.

## 4. Identity

Audit references must resolve to the appropriate Jano identity context without turning the audit system into identity authority.

## 5. Clinical Actions

Consequential clinical actions must remain attributable to responsible actors and the owning clinical domains.

## 6. AI

AI-assisted activity should preserve AI request/recommendation/review/action provenance where required. AI output is not automatically clinical truth.

## 7. Offline

Offline actions require local accountability and later reconciliation while preserving historical integrity.

## 8. Corrections

Corrections/amendments should leave an explainable history rather than silently overwrite prior accountability.

## 9. Data Platform

Audit evidence can be consumed downstream for reporting/analytics, but downstream consumers do not own operational accountability semantics.

## 10. Non-Goals

No exact log schema, retention duration, SIEM product, immutable storage design, or API contract is finalized here.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
