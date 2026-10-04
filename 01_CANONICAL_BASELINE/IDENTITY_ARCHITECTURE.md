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
