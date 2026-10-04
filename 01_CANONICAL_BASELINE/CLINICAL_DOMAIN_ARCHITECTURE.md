# CLINICAL_DOMAIN_ARCHITECTURE.md

**Version:** v0.1.2
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Purpose

Define the clinical domain landscape without prematurely finalizing every capability as a bounded context.

## 2. Ownership Principle

Clinical domains own clinical meaning and authoritative state for that meaning. Platform layers provide supporting capabilities without absorbing clinical business logic.

## 3. Clinical Landscape

Registration, Identity/EMPI interaction, Triage, Encounter, Assessment, Diagnosis, Treatment, Medication, Referral, and Follow-up form the initial clinical landscape. Laboratory, Radiology, Pharmacy, Emergency, Maternal Health, Newborn/Child Health, Infectious Disease, Chronic Disease, Public Health, Community Health, and Appointments are future or adjacent candidates.

## 4. Workflow Classification

Workflow stage, clinical capability, domain candidate, supporting platform capability, and cross-domain concern must remain distinct.

## 5. Clinical Decision Support

CDS is a clinical/workflow capability. AI-assisted CDS is one support mechanism, not the definition of CDS.

## 6. Longitudinal State

Longitudinal clinical problems/conditions and care plans must not be inferred to belong to Encounter merely because they are used during an encounter.

## 7. Offline-First

Each clinical domain must respect offline continuity and domain-specific conflict semantics.

## 8. Open Questions

Final bounded contexts, longitudinal ownership, Diagnosis ownership, Treatment ownership, Medication separation, Referral separation, and follow-up semantics remain subject to explicit DDD evidence.
## 9. Clinical Domain Ownership Matrix

| Area | Meaning/owner maturity |
|---|---|
| Encounter | Approved bounded context |
| Assessment | Approved secondary aggregate baseline within Encounter context |
| Diagnosis / Clinical Conclusion | Candidate / evidence-driven |
| Treatment | Candidate / evidence-driven |
| Medication Management | Candidate clinical domain with lifecycle outside Encounter |
| Referral / Care Coordination | Candidate clinical domain/capability with own lifecycle |
| Follow-up | Candidate continuity capability; final ownership open |
| Laboratory | Candidate future domain |
| Radiology | Candidate future domain |
| Pharmacy | Candidate future domain/capability |
| Emergency | Candidate future domain/capability |
| Maternal / Child / Public Health | Specialty/program/candidate domains requiring later analysis |

## 10. Clinical State Authority

Authoritative clinical state is owned by the relevant clinical domain or aggregate. Healthcare OS does not become a universal clinical state owner.

## 11. Domain Interaction

Clinical workflows coordinate domains using domain events, workflow/domain reactions, and domain-owned commands. A workflow relationship does not transfer ownership of state.

## 12. Clinical Documentation

Documentation is governed by the domain that owns the meaning of the documented state. AI-generated material remains distinguishable from clinician-authored or accepted clinical information.

## 13. Clinical Safety

Clinical safety applies to both deterministic CDS and AI-assisted CDS. Supporting mechanisms must not silently become clinical authority.

## 14. Offline Rules

Each domain determines safe local operation and conflict semantics appropriate to its meaning. A generic synchronization policy cannot override clinical domain rules.

## 15. Future Domain Promotion Criteria

Promotion from candidate to approved bounded context requires sufficient evidence of independent meaning, ownership, state, invariants, lifecycle, correction semantics, and coordination boundaries.

## 16. Canonical Status

**Approved Architectural Baseline — v0.1.2**
