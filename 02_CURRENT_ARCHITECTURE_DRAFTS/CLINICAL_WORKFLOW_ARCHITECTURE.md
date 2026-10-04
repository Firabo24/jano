# CLINICAL_WORKFLOW_ARCHITECTURE.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Healthcare OS / Clinical Domains

## 1. Purpose

Define workflow as coordination across capabilities/domains without creating a hidden central domain.

## 2. Workflow vs Domain

A workflow is a sequence of activities. A domain owns meaning and state. A workflow can cross multiple bounded contexts.

## 3. Clinical Example

```text
Registration
  ↓
Identity / EMPI
  ↓
Encounter / Triage / Assessment
  ↓
CDS / Diagnosis
  ↓
Treatment / Medication
  ↓
Referral / Follow-up
```

## 4. Coordination Pattern

```text
Aggregate / Domain Event
        ↓
Workflow or Domain Reaction
        ↓
Command to Owning Context
```

## 5. No Central Clinical Owner

Workflow orchestration must not absorb the authoritative state of the domains it coordinates.

## 6. AI

AI is optional supporting intelligence in workflows and cannot be a mandatory dependency for essential care.

## 7. Offline

Workflow execution must account for local operation, delayed synchronization, and domain-specific conflicts.

## 8. Human Accountability

Workflow steps may involve multiple actors. Clinical responsibility remains explicit and distinct from authorization.

## 9. Corrections

Workflow history does not replace domain correction semantics.

## 10. Non-Goals

No exact workflow engine, BPMN implementation, service choreography, API sequence, or UI orchestration is finalized here.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
