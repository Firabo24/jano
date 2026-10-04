# SECURITY_ARCHITECTURE.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Jano Core / Identity / Authorization / Consent / Trust

## 1. Purpose

Define the cross-cutting security boundary across Jano Health while preserving Jano Core as the owner of foundational identity, authorization, consent, and trust primitives.

## 2. Security Model

Security is cross-cutting. The conceptual chain is:

```text
Identity
  ↓
Authentication
  ↓
Authorization / Consent / Trust Context
  ↓
Governed Operation
  ↓
Accountability / Audit
```

## 3. Foundational vs Cross-Cutting

Jano Core contains foundational security-related capabilities that are required by multiple domains. Detailed policy enforcement, application hardening, device security, network controls, and operational security remain cross-cutting concerns.

## 4. Clinical Boundary

Clinical domains own clinical meaning. Security controls do not define clinical correctness or clinical authority.

## 5. Identity Boundary

Person, workforce, facility, and external identity relationships come from the Jano Core identity boundary. Fayda remains external.

## 6. Authorization Boundary

Authorization determines permission to request/perform an operation. It does not override domain invariants or clinical responsibility.

## 7. Consent and Trust

Consent governs permitted use/disclosure/processing. Trust is contextual and does not become a replacement for identity, authorization, or clinical correctness.

## 8. Audit and Accountability

Security-relevant and clinically consequential operations must remain attributable and auditable. Audit is evidence of accountability, not a substitute for domain history.

## 9. Offline Security

Offline-first must preserve identity, authorization, trust, and audit safeguards without assuming constant connectivity. Local security state is not automatically globally reconciled security truth.

## 10. AI Security

AI access must be scoped to authorized clinical context. AI may assist decisions but cannot bypass governance or clinical ownership.

## 11. Data Protection

Data Platform consumes governed data and must apply appropriate privacy and access controls. It does not become identity or clinical authority.

## 12. Interoperability Security

External systems are isolated behind the interoperability boundary. External trust/identity is translated into Jano governance rather than implicitly trusted.

## 13. Non-Goals

No detailed cipher suite, token format, policy-engine implementation, network topology, IAM product selection, database security schema, or deployment hardening plan is finalized here.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
