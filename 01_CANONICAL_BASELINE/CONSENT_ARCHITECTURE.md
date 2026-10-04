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
## 7. Consent Meaning

Consent represents permitted or constrained use, disclosure, or processing within an explicitly governed purpose and scope. It is not a blanket permission to perform any action.

## 8. Consent Context

Conceptual consent context may include:

- purpose;
- scope;
- subject/person;
- actor or recipient context where applicable;
- temporal applicability;
- status;
- provenance;
- correction/amendment history.

## 9. Lifecycle

```text
Established → Active → Withdrawn / Expired
```

The exact lifecycle can vary by governed consent type, but withdrawal/expiry must not be confused with historical erasure.

## 10. Consent vs Authorization

Authorization answers whether an actor may perform an operation. Consent provides a governance basis or constraint concerning use/disclosure/processing. Both may be required and neither replaces domain validity.

## 11. Consent vs Clinical Authority

Consent does not itself create clinical authority or make a clinical decision correct.

## 12. AI

AI may consume applicable consent context. AI cannot infer unrestricted consent from the mere existence of patient data.

## 13. Data Platform

Secondary data use must remain subject to applicable consent and governance constraints. Data Platform does not redefine consent meaning.

## 14. Interoperability

External consent representations can be translated at the integration boundary; the resulting internal meaning remains governed by Jano consent architecture.

## 15. Offline

Local consent state may support continuity but does not automatically equal globally reconciled consent truth.

## 16. Canonical Status

**Approved Architectural Baseline — v0.1.0**
