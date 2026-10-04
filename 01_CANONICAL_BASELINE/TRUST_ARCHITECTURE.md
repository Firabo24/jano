# TRUST_ARCHITECTURE.md

**Version:** v0.1.0
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture  
**Parent Architecture:** Jano Core

## 1. Purpose

Trust is a contextual governance concept built from relevant identity, authentication, authorization, consent/governance, accountability/audit, and operational context.

## 2. Model

```text
Identity + Authentication + Authorization + Consent/Governance + Accountability/Audit
        ↓
Trust Context
        ↓
Permitted / Governed Operation
```

## 3. Distinctions

Trust is not identity, authentication, authorization, consent, audit, clinical responsibility, clinical validity, or clinical correctness.

## 4. Scope

Trust context is scoped to actor, context, operation, and time. It is not a giant entity containing all underlying states.

## 5. Lifecycle

```text
Trust Context Established
        ↓
Active / Applicable
        ↓
No Longer Applicable
```

## 6. External Trust

External trust relationships do not automatically become internal Jano Trust Authority. Fayda remains an external identity provider.

## 7. AI

AI output is not Trusted Clinical Truth merely because it passed a trust context.
