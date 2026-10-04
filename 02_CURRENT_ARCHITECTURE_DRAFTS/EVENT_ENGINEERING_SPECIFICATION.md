# EVENT_ENGINEERING_SPECIFICATION.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Domain Event Infrastructure

## 1. Purpose

Consolidate conceptual event rules already established across the architecture.

## 2. Event Semantics

A domain event is a fact that an authoritative domain state change occurred.

## 3. Ownership

The owning aggregate/domain defines meaning. Core Event Infrastructure defines propagation capabilities.

## 4. Historical Integrity

Events and related audit evidence must preserve historical chronology and provenance.

## 5. Duplicate Safety

Same event delivered more than once is not equivalent to multiple clinical events occurring.

## 6. Ordering

No global total order is assumed. Aggregate causal ordering and clinical chronology remain distinct.

## 7. Cross-Aggregate Reaction

Events coordinate through reactions and commands, not direct mutation.

## 8. Offline

Local event generation can precede global propagation. Reconciliation occurs under domain governance.

## 9. Non-Goals

No event envelope schema, broker, transport, serialization, or database event-store design is finalized.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
