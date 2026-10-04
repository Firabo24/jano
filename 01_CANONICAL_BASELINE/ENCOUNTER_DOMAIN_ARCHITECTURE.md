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
