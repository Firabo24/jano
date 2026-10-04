# ARCHITECTURE_VIEW_CATALOG.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Jano Health Master Architecture

## 1. Purpose

Organize the architecture into views without creating new domains.

## 2. Structural View

Shows Jano Health, Healthcare OS, Jano Core, AI Platform, Data Platform, and Interoperability, with logical ownership boundaries.

## 3. Domain View

Shows clinical bounded-context candidates and their maturity without implying every capability is a bounded context.

## 4. Identity View

Shows Jano Core Identity Boundary, Patient Identity, Identity Representations, EMPI, Fayda external relationship.

## 5. Event View

Shows domain-owned event meaning connected through Core Event Infrastructure.

## 6. Runtime View

Shows interactions while distinguishing them from structural dependency.

## 7. Offline View

Shows local operation, later synchronization, conflict detection, and domain interpretation.

## 8. Security / Trust View

Shows identity, authentication, authorization, consent, trust, accountability, and cross-cutting security.

## 9. Data View

Shows domain-owned clinical state flowing downstream into governed analytics/research capabilities.

## 10. Interoperability View

Shows external systems entering/leaving through explicit translation boundaries.

## 11. Decision View

Maps architecture views to ADRs and current maturity status.

## 12. Non-Goals

No new architecture boundary or deployment design is introduced by the view catalog.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
