# CLINICAL_DDD_ARCHITECTURE.md

**Version:** v0.1.3
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Purpose

Define the Domain-Driven Design direction for the clinical architecture.

## 2. DDD Starting Point

DDD analysis proceeds from clinical meaning, ownership, lifecycle, consistency boundaries, workflow interactions, and event boundaries rather than database tables, existing code, microservice popularity, or infrastructure preference.

## 3. Domain Distinctions

```text
Clinical Domain
Clinical Capability
Clinical Workflow
Bounded Context
Aggregate
Domain Event
```

These are related but not interchangeable concepts.

## 4. Candidate Clinical Landscape

Current candidates include Patient Administration / Registration, Clinical Encounter, Clinical Assessment, Diagnosis, Treatment / Care Planning, Medication Management, Referral / Care Coordination, Follow-up / Continuity, Laboratory, Radiology, Pharmacy, Emergency, public-health and specialty/program capabilities.

This landscape is provisional where evidence is insufficient.

## 5. Longitudinal vs Encounter State

Encounter state is not the same as longitudinal condition/problem state. Longitudinal state ownership remains subject to later DDD analysis.

## 6. Aggregate Rule

An aggregate should be separated only when invariant set, consistency requirement, concurrency profile, safety semantics, and offline behavior collectively demonstrate that separation improves domain correctness more than it increases coordination.

Safety sensitivity alone, lifecycle independence alone, or a domain noun alone does not justify separation.

## 7. Cross-Aggregate Coordination

```text
Aggregate A
    ↓
Domain Event
    ↓
Workflow / Domain Reaction
    ↓
Command
    ↓
Aggregate B
```

Direct internal mutation between aggregates is prohibited.

## 8. Architecture Maturity

Candidate, Strong Candidate, Primary, Keep Inside Primary, Rejected Pattern, and Approved are distinct maturity concepts.

## 9. Rejected Extremes

One Giant Aggregate is rejected. One Aggregate Per Noun is rejected.

## 10. Constraints

No detailed implementation technology is established by this DDD document.
