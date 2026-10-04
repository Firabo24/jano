# PUBLISHER_CONSUMER_MATRIX.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Domain Event Infrastructure

## 1. Purpose

Record conceptual publisher/consumer relationships without treating them as hard deployment contracts.

## 2. Conceptual Matrix

| Publisher | Consumers / Reactions | Ownership note |
|---|---|---|
| Identity | Clinical domains, Data, authorized workflows | Consumers interpret identity impact |
| Encounter | Assessment, workflow, Data, AI as appropriate | Encounter retains lifecycle authority |
| Assessment | Encounter workflow, Data, CDS as appropriate | Assessment retains finding authority |
| AI | Clinical review, Audit, Data as governed | AI output remains advisory |
| Consent | Clinical/Data/AI/Interop as governed | Consent meaning remains Core-owned |

## 3. Rule

A subscription/reaction does not transfer ownership of the published state.

## 4. Non-Goals

No messaging technology, topic name, queue name, API contract, or retry implementation is finalized.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
