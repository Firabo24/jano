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
## 7. Trust Inputs

Trust context can incorporate:

- identity;
- authentication state;
- authorization context;
- consent/governance context;
- accountability/audit context;
- facility/organizational context;
- operation and time.

These remain separate authoritative concepts.

## 8. Trust Is Contextual

Trust is evaluated for an actor, operation, resource/context, and time. It is not a permanent property of a user or device and is not a replacement for downstream domain checks.

## 9. Trust vs Authorization

Trust can inform whether an operation may proceed, but an authorization relationship remains independently governed and a clinical domain must still validate its own command.

## 10. Trust vs Clinical Responsibility

Trust does not make an actor clinically responsible for every action, nor does it transfer professional accountability between actors.

## 11. External Trust

External system trust relationships are governed at integration boundaries. Trust in an external identity or system does not automatically grant that system internal Jano authority.

## 12. Offline

Offline trust may be locally evaluated from available context. Local evaluation must be distinguishable from globally reconciled trust state.

## 13. AI

AI assistance operates within an already governed context. AI does not become a trust authority merely because it produces a recommendation.

## 14. Audit

Material trust-context changes or decisions may generate accountability representations, while audit remains separate from trust meaning.

## 15. Canonical Status

**Approved Architectural Baseline — v0.1.0**
