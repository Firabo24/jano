# ENCOUNTER_DOMAIN_ARCHITECTURE.md

**Version:** v0.1.0
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Purpose

Define Encounter as a bounded clinical domain focused on an individual clinical interaction.

## 2. Core Definition

Encounter is an individual clinical interaction / care event.

```text
Encounter ≠ Visit
Encounter ≠ Universal Episode of Care
```

## 3. Encounter Owns

- identity of the encounter;
- valid patient association;
- lifecycle/status;
- temporal scope;
- care setting/classification;
- participation/accountability;
- reason/context;
- encounter-level assessment findings where part of the approved boundary;
- encounter-level diagnostic conclusions;
- encounter-level treatment intent/actions;
- MVP triage result;
- disposition;
- completion and closure.

## 4. Encounter Does Not Own

Jano Core identity/EMPI, longitudinal conditions, medication lifecycle outside Medication Management, referral lifecycle, care plans, pharmacy state, external laboratory/radiology semantics, AI output, CDS recommendations, analytics ownership, or interoperability representations.

## 5. Lifecycle Principles

Create Encounter establishes identity, patient association, initial lifecycle, temporal scope, and attribution. Create Encounter is not equivalent to Start Encounter.

Completion is not closure. Post-closure correction, amendment, late documentation, and reopening are distinct concepts.

## 6. MVP Triage

Current MVP triage result remains inside Encounter because it is part of the encounter entry/lifecycle context. Triage is not itself a separate bounded context.

## 7. Coordination

Cross-context behavior uses domain events, workflow/domain reactions, and commands. Direct cross-aggregate mutation is prohibited.
## 7. Encounter Definition

An Encounter is an individual clinical interaction or care event occurring within a defined temporal and clinical context.

```text
Encounter ≠ Visit
Encounter ≠ Universal Episode of Care
Encounter ≠ Longitudinal Patient State
```

## 8. Ownership Boundary

Encounter owns:

- encounter identity and patient association;
- lifecycle/status;
- temporal scope;
- care setting/classification;
- participation/accountability;
- reason/context;
- encounter-level assessment findings where within the approved aggregate boundary;
- encounter-level diagnostic conclusions at the maturity permitted by the architecture;
- encounter-level treatment intent/actions at the maturity permitted by the architecture;
- MVP triage result;
- disposition;
- completion and closure.

## 9. Explicit Non-Ownership

Encounter does not own Jano Core identity foundations, EMPI, longitudinal conditions, Medication Management lifecycle, Referral lifecycle, care-plan ownership outside Encounter semantics, external lab/radiology representations, AI outputs, Data Platform analytics, or Interoperability contracts.

## 10. Primary Aggregate

The Encounter Aggregate protects the indivisible lifecycle invariant of:

```text
Identity + Patient Association + Lifecycle + Status + Temporal Scope + Completion + Closure
```

The approved architecture further retains participation, reason/context, MVP triage, disposition, and related Encounter-entry/accountability semantics inside the primary aggregate.

## 11. Triage

Triage remains a clinical workflow/capability. In the current MVP, its result is Encounter-owned. Triage is not the same thing as diagnosis or prescription.

## 12. Participation and Reason

Participant/accountability relationships and reason/context remain inside Encounter because their correctness depends on the Encounter's own lifecycle and entry meaning. Actor identity remains outside Encounter.

## 13. Completion and Closure

Completion and closure are distinct. Completion records clinical work reaching a completed state; closure is a stronger historical/accountability boundary.

## 14. Correction

Correction/amendment of Encounter-owned state follows aggregate-owned semantics. Post-closure correction does not automatically mean reopening the Encounter or creating a new encounter.

## 15. Offline Operation

Offline acceptance is valid only when the domain command satisfies local domain rules. It does not imply conflict-free global reconciliation.

## 16. Cross-Aggregate Relationships

Assessment, Medication, Referral, and other separate lifecycles interact with Encounter through coordination rather than direct internal mutation.

## 17. Runtime vs Structure

Clinical workflow interaction with Encounter does not imply structural ownership by Encounter. Structural dependency, runtime interaction, event flow, and external integration remain distinct.

## 18. Open Questions

Longitudinal state, final diagnosis ownership, treatment ownership, and future domain boundaries remain subject to dedicated architecture review.

## 19. Canonical Status

**Approved Architectural Baseline — v0.1.0**
