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
