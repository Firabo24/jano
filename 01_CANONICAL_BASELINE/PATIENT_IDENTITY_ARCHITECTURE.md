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
