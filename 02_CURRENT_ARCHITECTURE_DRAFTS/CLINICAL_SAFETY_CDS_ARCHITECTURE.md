# CLINICAL_SAFETY_CDS_ARCHITECTURE.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Healthcare OS / AI Platform / Jano Core governance

## 1. Purpose

Define Clinical Decision Support as a clinical/workflow capability broader than AI and preserve clinician accountability.

## 2. CDS Boundary

CDS supports clinical decision-making through guidelines, rules, calculations, alerts, evidence, and AI assistance where appropriate.

## 3. Core Model

```text
Clinical Workflow
        ↓
Clinical Decision Support
        ↓
Authorized Clinical Context
        ↓
AI Assistance where appropriate
        ↓
Safety / Validation
        ↓
Clinician Review
        ↓
Clinical Action
```

## 4. AI Relationship

AI is optional supporting intelligence within CDS. The workflow must not statically depend on the AI Platform.

## 5. Clinical Safety

Safety must account for both non-AI and AI-assisted support. Supporting intelligence must not silently become clinical authority.

## 6. Human Oversight

Clinicians remain accountable for clinical decisions. AI output does not automatically become authoritative clinical record content.

## 7. Explainability and Uncertainty

Recommendations must preserve provenance and meaningful uncertainty. Confidence is a decision-support signal, not proof of clinical correctness.

## 8. Offline Operation

CDS must distinguish mechanisms that can remain available offline from capabilities requiring unavailable services. Essential care must continue if AI is unavailable.

## 9. Clinical Ownership

The clinical domain owning the affected clinical state remains authoritative for correction and final clinical action.

## 10. AI Events and Audit

AI may generate supporting audit/events, but AI event meaning remains AI-owned while clinical event meaning remains clinical-domain-owned.

## 11. Non-Goals

No exact AI models, prompts, clinical algorithms, scoring thresholds, autonomous clinical action model, or database/API design is finalized here.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
