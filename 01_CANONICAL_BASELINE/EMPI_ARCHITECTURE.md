# EMPI_ARCHITECTURE.md

**Version:** v0.1.3
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture  
**Parent Architecture:** Jano Core / Identity Architecture / Patient Identity Architecture

## 1. Purpose

Define the Enterprise Master Patient Index capability within Jano Health without creating a second identity authority.

## 2. Central Architectural Principle

```text
Jano Core — Identity Boundary
        │
        ├── Person Identity
        ├── Patient Relationship
        ├── Identity Representations
        └── EMPI Capability
              ├── Evaluation
              ├── Candidate Relationships
              └── Reconciliation
```

Jano Core remains the authoritative internal identity boundary. EMPI operates inside it and does not replace the broader Patient Identity Architecture.

## 3. Core Identity Distinctions

```text
Identity Representation ≠ Person ≠ Identity Equivalence Decision
Potential Duplicate ≠ Confirmed Match ≠ Confirmed Different Person
Identity Data ≠ Matching Evidence ≠ Match Decision
Evaluation Operation ≠ Domain Command
Evidence ≠ Decision
```

## 4. Resolution Flow

```text
Multiple Identity Representations
        ↓
Identity Evaluation
        ↓
Evidence / Candidate
        ↓
Governed Reconciliation
        ↓
Identity Relationship Decision
```

Evaluation output is not automatically authoritative identity state. Candidate results are not automatically persisted.

## 5. Evaluation Operations

- Compare Identity Representations
- Evaluate Identity Evidence

These are evaluation capabilities, not domain commands.

## 6. Relationship Outcomes

```text
Confirmed Same Person
Confirmed Different Persons
Possible / Candidate Match
Unresolved
Rejected Match
Identity Conflict
```

## 7. Relationship Lifecycle

```text
Candidate / Possible
        ↓
Evaluated
        ↓
Confirmed / Established
```

This is conceptual, not mandatory for every relationship. An established relationship may later be amended, corrected, invalidated, or superseded where applicable.

## 8. Representation Status

```text
Active / Applicable
Superseded
Invalidated where applicable
```

Relationship outcome, relationship lifecycle, and representation status remain distinct.

> **Relationship status must not be confused with Person status or Representation Status.**

## 9. Reconciliation vs Link

```text
Identity Evaluation
        ↓
Candidate / Evidence
        ↓
Governed Reconciliation
        ↓
Identity Relationship Decision
```

Reconciliation is the governed process/operation that establishes the relationship outcome. Link is a resulting governed identity relationship where appropriate.

## 10. Merge

Merge is not the default meaning of a match. No destructive merge by default. Historical lineage must be preserved.

## 11. Wrong-Person Association

Wrong-person association is distinct from duplicate identity representation. EMPI does not directly mutate Encounter, Assessment, Medication, Referral, or other clinical aggregates.

## 12. Fayda

Fayda remains external. External identity evidence does not automatically redefine Jano Person Identity.

## 13. Offline

```text
Local Identity State ≠ Globally Reconciled Identity State
Offline Duplication ≠ Multiple Real Persons
```

## 14. AI / Data Platform / Events

AI may assist evaluation but cannot become identity authority. Data Platform remains downstream. Identity event meaning remains identity-owned. Core Event Infrastructure provides infrastructure only.

## 15. Non-Goals

No matching algorithm, database schema, API design, synchronization algorithm, Fayda implementation, security implementation, or deployment design is defined here. Anchor remains completely outside Jano.

## 16. Final Status

**DRAFT v0.1.3 — formal review pending.**
