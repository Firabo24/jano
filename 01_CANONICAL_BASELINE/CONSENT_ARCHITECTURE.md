# CONSENT_ARCHITECTURE.md

**Version:** v0.1.0
**Status:** Approved Architectural Baseline
**Document Owner:** Jano Health Architecture  
**Parent Architecture:** Jano Core

## 1. Purpose

Consent is a foundational governance capability representing permitted or constrained use, disclosure, or processing within a defined purpose, scope, actor/context, and temporal meaning.

## 2. Distinctions

```text
Consent ≠ Identity
Consent ≠ Authentication
Consent ≠ Authorization
Consent ≠ Clinical Decision
```

## 3. Lifecycle

```text
Established → Active → Withdrawn / Expired
```

Correction and amendment are distinct.

## 4. Ownership

Jano Core owns foundational consent meaning. Clinical domains consume governance but retain clinical meaning/state.

## 5. AI / Data / Interoperability

AI may consume consent context but cannot infer unrestricted consent. Data Platform is downstream. Interoperability translates external consent into internal meaning at a boundary.

## 6. Offline

Offline consent state may support continuity but is not automatically globally reconciled governance state.
