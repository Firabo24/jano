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
## 8. Bounded Context Analysis

A bounded context is a semantic and ownership boundary inside which a model has consistent meaning. It is not synonymous with a clinical capability, workflow, aggregate, database, module, or service.

## 9. Aggregate Evidence Framework

The current architecture uses the following maturity categories:

```text
Primary Aggregate
Strong Aggregate Candidate
Aggregate Candidate
Keep Inside Primary Aggregate
Future Aggregate Candidate
Rejected Aggregate Pattern
```

Approval is a separate governance act.

## 10. Encounter Aggregate

The Encounter Aggregate is the approved primary aggregate baseline within the approved Encounter bounded context.

Its protected invariant family includes:

```text
Encounter Identity
+
Patient Association
+
Lifecycle
+
Status
+
Temporal Scope
+
Participation / Accountability
+
Reason / Context
+
Current MVP Triage
+
Disposition
+
Completion
+
Closure
```

## 11. Assessment Aggregate

Assessment is the approved secondary aggregate baseline. Its invariant family is:

```text
Assessment Lifecycle
+
Findings
+
Finding Attribution
+
Clinical Meaning
+
Correction / Amendment Integrity
```

## 12. Clinical Conclusion and Treatment

These remain lower-maturity candidates where the current evidence requires further validation. The architecture does not create separate aggregates merely because conclusion or treatment is safety-sensitive or has a distinct lifecycle.

## 13. Rejected Extremes

### One Giant Aggregate

Rejected because it increases contention, broadens invariants unnecessarily, amplifies offline conflict, and makes correction/evolution semantics excessively coupled.

### One Aggregate Per Noun

Rejected because it creates fragmentation, coordination overhead, invariant leakage, unnecessary events, and more difficult offline reconciliation.

## 14. Cross-Aggregate Coordination

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

Direct internal mutation across aggregates is prohibited as an architectural rule.

## 15. Convenience vs Consistency

State must not be included in an aggregate merely because it is displayed together, created together, or frequently used together. Aggregate membership requires a demonstrated consistency relationship.

## 16. Offline Considerations

Aggregate ownership remains domain-driven during offline operation. Synchronization can identify conflicts and transport facts, but it does not determine clinical meaning.

## 17. State-Model Validation

Aggregate boundary decisions must be tested through state models, including completion, closure, correction, amendment, late documentation, cross-aggregate interaction, concurrent changes, and offline conflict scenarios.

## 18. Event Ownership

The bounded context/aggregate that owns a business state change owns the semantic meaning of the resulting domain event. Platform event infrastructure is not a domain-event owner.

## 19. ADR Discipline

Architecture decision records should express a decision, evidence, consequences, and maturity. A recommendation or strong candidate is not automatically an approved decision.

## 20. DDD Non-Goals

This document does not choose databases, APIs, microservices, deployment topology, synchronization algorithms, or specific framework boundaries.

## 21. Canonical Status

**Approved Architectural Baseline — v0.1.3**
