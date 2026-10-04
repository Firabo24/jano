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
