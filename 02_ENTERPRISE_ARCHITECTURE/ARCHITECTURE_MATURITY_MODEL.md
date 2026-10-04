# Architecture Maturity Model

**Document category:** Enterprise Architecture  
**Status:** Draft for Architectural Review  
**Version:** v0.2.0

## Purpose
Provide a uniform maturity vocabulary for distinguishing ideas, supported candidates, reviewed drafts and approved architectural authority.

## Maturity Levels

| Level | Meaning | Required evidence |
|---|---|---|
| Concept | Idea or future possibility | Problem/context only |
| Candidate | Plausible boundary or capability under analysis | Ownership and boundary hypothesis |
| Draft for Review | Substantive document exists | Boundary, responsibilities, dependencies, risks and open questions |
| Reviewed | Architectural review completed with recorded corrections | Review evidence and resolved material contradictions |
| Approved Architectural Baseline | Explicitly accepted authority | Approval record/version and consistency with dependent artifacts |
| Superseded | Former baseline replaced by a later approved version | Replacement reference and preserved history |
| Deferred | Intentionally postponed | Reason and trigger for revisit |
| Legacy / Not Canonical | Historical material not governing current design | Explicit non-authoritative label |

## Promotion Rules
Promotion requires evidence of consistency with higher-level architecture, clear ownership, no forbidden boundary leakage, treatment of offline/security/safety implications where relevant, and an explicit review decision. Presence in the repository does not equal approval.

## Demotion / Correction
A baseline may be superseded or corrected through governed change control. Historical versions remain traceable. Approval status is not itself a claim that implementation is complete.

## Status
Draft for Architectural Review.
