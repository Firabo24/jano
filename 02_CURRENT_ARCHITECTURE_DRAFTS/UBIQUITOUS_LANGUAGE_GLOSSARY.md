# UBIQUITOUS_LANGUAGE_GLOSSARY.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Jano Health Architecture / DDD / Identity

## 1. Purpose

Provide a controlled shared vocabulary for concepts that have been repeatedly distinguished across Jano Health architecture.

## 2. Core Terms

| Term | Meaning | Not the same as |
|---|---|---|
| Person Identity | Authoritative internal representation of a person | Patient Relationship, Representation |
| Patient Relationship | A person’s healthcare relationship with Jano | Person Identity |
| Identity Representation | A representation of identity information | Person, Decision |
| EMPI | Identity-resolution capability inside Jano Core | Separate identity authority |
| Candidate Match | Possible relationship produced by evaluation | Confirmed relationship |
| Reconciliation | Governed process/operation that establishes a relationship | Link |
| Link | Resulting governed identity relationship where appropriate | Reconciliation process |
| Superseded | Representation status | Relationship outcome |
| Encounter | Individual clinical interaction / care event | Universal episode |
| Assessment | Findings/meaning lifecycle within its own aggregate boundary | Encounter lifecycle |
| CDS | Clinical decision-support capability | AI itself |
| Trust Context | Contextual trust assessment | Clinical correctness |
| Domain Event | Fact of domain state change | Event infrastructure |
| Offline State | Local operational state under connectivity constraints | Global reconciliation |

## 3. Core Distinctions

```text
Authentication ≠ Authorization ≠ Consent ≠ Clinical Responsibility
Evidence ≠ Decision
Evaluation ≠ Command
Relationship Outcome ≠ Relationship Lifecycle ≠ Representation Status
Aggregate ≠ Bounded Context
Workflow ≠ Domain
```

## 4. Governance

The glossary is subordinate to authoritative architecture documents; where future reviewed documents refine a term, the glossary must be updated rather than silently changing meaning.

## 5. Non-Goals

No exhaustive clinical terminology dictionary is attempted here.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
