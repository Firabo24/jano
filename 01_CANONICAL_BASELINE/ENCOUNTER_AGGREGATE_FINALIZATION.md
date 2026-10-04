# ENCOUNTER_AGGREGATE_FINALIZATION.md

**Version:** v0.1.0
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture

## 1. Finalization Principle

Completion establishes that required encounter work has been completed. Closure establishes a stronger historical/accountability boundary.

## 2. Completion

Completion belongs to the Encounter Aggregate and remains distinct from closure.

## 3. Closure

Closure belongs to the Encounter Aggregate and protects the historical/accountability boundary.

## 4. Post-Closure

Post-closure correction, amendment, late documentation, new clinical information, and reopening are not interchangeable.

## 5. Integrity

Historical identity and clinical chronology must be preserved. Later changes must remain explainable rather than silently rewriting history.

## 6. Cross-Aggregate Rule

Another aggregate must not directly mutate finalization state.
