# IDENTITY_ARCHITECTURE.md

**Version:** v0.1.0
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture  
**Parent Architecture:** Jano Core

## 1. Scope

Identity Architecture defines Jano's internal identity foundations.

## 2. Identity Types

- Person / Patient Identity
- Workforce / User Identity
- Facility / Organization Identity
- External Identity Relationships

## 3. Core Distinctions

```text
Identity
    ≠ Authentication
    ≠ Authorization
    ≠ Consent
    ≠ Clinical Responsibility
```

## 4. Internal Authority

Jano Core owns the internal identity boundary. External identity providers remain external relationships.

## 5. Fayda

Fayda is an external identity provider and relationship, not the Jano internal identity model.

## 6. EMPI

EMPI is a capability inside the identity consistency boundary. It does not replace the broader Patient Identity architecture.

## 7. Correction and Reconciliation

Identity correction, identity reconciliation, and wrong-person clinical association are distinct concepts.

## 8. Offline

Local identity state may be used offline but is not automatically globally reconciled identity truth.
## 9. Identity Models

Jano recognizes distinct identity types:

```text
Person / Patient Identity
Workforce / User Identity
Facility / Organization Identity
External Identity Relationships
```

These types may relate, but none is interchangeable with another.

## 10. Identity vs Clinical State

Identity identifies the subject or actor. Clinical state describes what is true or recorded about care. Identity does not own Encounter, Assessment, Medication, Referral, or other clinical state simply because it references those identities.

## 11. Person Identity

Person Identity is the authoritative internal identity concept for the human individual represented within Jano. A duplicate representation does not by itself prove that two people are different or that two records must be merged.

## 12. Patient Relationship

The healthcare relationship with a person is distinct from the underlying person identity. A person can have representations and healthcare relationships without creating a second person authority.

## 13. Identity Representations

A representation is a contextual record or identifier that refers to a person. Representation status can change without changing the person's identity.

## 14. Reconciliation

```text
Representations
   ↓
Evaluation
   ↓
Evidence / Candidate
   ↓
Governed Reconciliation
   ↓
Identity Relationship Decision
```

## 15. Correction

Identity correction is not ordinary editing and is not a synonym for duplicate merging. Wrong-person clinical association is a separate high-consequence problem.

## 16. External Identity

External identity systems remain external relationships. Evidence received from an external provider does not become the internal Jano identity model without governed interpretation.

## 17. Offline

Local identity state can support continuity. It does not become global identity truth merely because a node accepts it locally.

## 18. Canonical Status

**Approved Architectural Baseline — v0.1.0**
