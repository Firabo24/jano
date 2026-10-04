# PATIENT_IDENTITY_ARCHITECTURE.md

**Version:** v0.1.1
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture  
**Parent Architecture:** Jano Core / Identity Architecture

## 1. Purpose

Define patient identity semantics and the consistency boundary that supports clinical attribution.

## 2. Identity Concepts

```text
Person Identity
      │
      ├── Patient Relationship
      └── Identity Representations
```

Internal Person Identifier identifies the authoritative Jano Person Identity. A Patient Relationship represents the person's healthcare relationship. A Patient Reference may serve clinical/domain-facing reference needs without becoming a second person-identity authority.

## 3. Identity Context Before Clinical Attribution

Clinical information must not be attributed without explicitly represented identity context. Context may be authoritative, provisional/local, or unresolved pending reconciliation as appropriate. Provisional/unresolved state must not silently become globally reconciled identity truth.

## 4. Identity Change Propagation

```text
Identity Change
    ↓
Identity Domain Event / Governed Identity Fact
    ↓
Clinical Domain Interpretation
    ↓
Domain-Owned Command / Correction
```

Identity does not directly mutate clinical aggregates.

## 5. Lifecycle

```text
Established → Active / Applicable → Inactive / No Longer Applicable
```

Inactivity of a patient relationship does not mean the underlying person ceased to exist.

## 6. Fayda and Offline

Fayda is external. Local identity state is not equivalent to global reconciliation.
## 6. Person Identity vs Patient Relationship

The authoritative internal Person Identity identifies the person. A Patient Relationship represents the person's healthcare relationship within Jano.

A Patient Reference may be used where a clinical/domain-facing reference is required, but it does not become a second person-identity authority.

## 7. Identity Representation Model

```text
Person Identity
      │
      ├── Patient Relationship
      │
      └── Identity Representations
```

An identifier or representation is evidence about identity, not identity equivalence itself.

## 8. Clinical Attribution Rule

Before clinical information is attributed, the system must have an explicit identity context. That context may be authoritative, provisional/local where appropriate, or unresolved pending reconciliation.

Provisional or unresolved identity context must not silently become globally reconciled identity truth.

## 9. Identity Change Propagation

```text
Identity Change
      ↓
Identity Domain Event / Governed Identity Fact
      ↓
Clinical Domain Interpretation
      ↓
Domain-Owned Command / Correction
```

Identity does not directly mutate clinical aggregates.

## 10. Lifecycle

```text
Established
    ↓
Active / Applicable
    ↓
Inactive / No Longer Applicable
```

Inactivity of a patient relationship or representation does not mean the human person ceased to exist.

## 11. Duplicate Representation

Multiple representations may refer to one person, different persons, or remain unresolved. A duplicate-looking representation is not itself a proof of sameness or difference.

## 12. Wrong-Person Association

Wrong-person association must be distinguished from duplicate representation and handled as a separate integrity/safety concern within the affected clinical domain.

## 13. Offline

Offline registration and identity use must preserve local provenance and reconciliation state. Synchronization does not decide identity equivalence.

## 14. Canonical Status

**Approved Architectural Baseline — v0.1.1**
