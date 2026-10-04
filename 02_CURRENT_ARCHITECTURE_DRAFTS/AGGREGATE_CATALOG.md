# AGGREGATE_CATALOG.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Clinical DDD / Encounter Domain Architecture

## 1. Purpose

Consolidate current aggregate findings for review.

## 2. Current Catalog

| Context | Aggregate | Maturity | Core protected meaning |
|---|---|---|---|
| Encounter | Encounter Aggregate | Primary | Encounter identity, patient association, lifecycle, status, temporal scope, completion, closure |
| Encounter | Assessment Aggregate | Strong Candidate | Assessment lifecycle, findings, attribution, clinical meaning, correction/amendment integrity |
| Encounter | Clinical Conclusion | Provisional Candidate | Encounter-level conclusion, subject to further evidence |
| Encounter | Treatment | Provisional Candidate | Encounter-level treatment intent/action, subject to further evidence |

## 3. Kept Inside Encounter Aggregate

Participant/accountability, Reason/Context, MVP Triage, Disposition, Completion, Closure.

## 4. External / Separate Clinical State

Medication state, Referral state, longitudinal conditions/problems, pharmacy state, external lab/radiology meaning remain outside Encounter Aggregate as appropriate.

## 5. Maturity Rule

No candidate is approved merely because a document labels it recommended. Separation requires evidence about invariants, consistency, concurrency, correction, offline behavior, safety, and coordination cost.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
