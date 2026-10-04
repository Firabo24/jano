# ENCOUNTER_COMMAND_ARCHITECTURE.md

**Version:** v0.1.1
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Purpose

Commands represent requests to change Encounter-owned state.

## 2. Command Model

```text
Actor
  ↓
Command
  ↓
Authorization / Responsibility Context
  ↓
Encounter Invariants
  ↓
State Change
  ↓
Domain Event
```

## 3. Core Command Semantics

Commands include the conceptual operations needed to create/initialize an encounter, advance lifecycle, record permitted encounter-owned information, complete, close, cancel where permitted, and perform constrained correction/amendment behavior.

## 4. Important Distinctions

- Authentication establishes actor identity.
- Authorization establishes permission.
- Clinical responsibility identifies accountable clinical participation.
- Command requests a state change.
- Event records a state change.

## 5. Cross-Aggregate Rule

Encounter commands cannot be replaced by another aggregate directly mutating Encounter state.

## 6. Offline

A valid offline command is not automatically a globally conflict-free command.
## 7. Command Definition

A Command is an explicit request to change state owned by an aggregate. It is not a technical API request, UI action, workflow notification, or event.

## 8. Encounter Command Boundary

Encounter commands may establish, advance, complete, close, correct, amend, or otherwise validly change Encounter-owned state according to approved domain semantics.

Examples include creation, arrival/entry, triage-related recording where Encounter-owned, documentation updates, completion, closure, constrained correction, and constrained amendment.

## 9. Command Preconditions

Conceptual preconditions include:

- valid identity context;
- valid patient association;
- valid lifecycle position;
- actor authorization context;
- domain invariants;
- required temporal meaning;
- applicable safety constraints;
- applicable offline validity rules.

Authorization alone does not make a command clinically valid.

## 10. Create vs Start

Create Encounter establishes Encounter identity, valid patient association, an initial lifecycle position, temporal scope, and attribution. It must not create an unassociated pending Encounter state.

Where Start Encounter is modeled separately, it represents a subsequent lifecycle transition rather than a duplicate identity-creation operation.

## 11. Correction and Amendment Commands

Correction addresses an error in existing state. Amendment records a permitted change or clarification after the original documentation. Late documentation records a prior occurrence later. These meanings must not be conflated.

## 12. Aggregate Boundary

A command can only change the aggregate that owns the relevant state. Cross-aggregate changes use coordination:

```text
Domain Event → Reaction / Workflow → Command → Receiving Aggregate
```

## 13. Offline Commands

Valid offline commands can be accepted locally subject to local rules. Local acceptance is not a guarantee of global reconciliation.

## 14. Command Non-Goals

This architecture does not prescribe API endpoints, transport protocols, framework classes, database transactions, or message-broker implementation.

## 15. Canonical Status

**Approved Architectural Baseline — v0.1.1**
