# Context and System Landscape

**Document category:** Enterprise Architecture  
**Status:** Draft for Architectural Review  
**Version:** v0.2.0

## Purpose
Describe Jano Health in its environment and distinguish internal architectural responsibilities from external systems and stakeholders.

## System Context

```text
Patients / Care Teams / Facilities
            │
            ▼
      ┌───────────────┐
      │  Jano Health  │
      └───────────────┘
        │    │    │
        │    │    └────► External Healthcare / National Systems
        │    └─────────► External Identity Relationships (e.g. Fayda)
        └──────────────► External Partners / Interoperability Counterparts
```

## Internal Platform Model

```text
Jano Health
├── Healthcare OS
├── Jano Core
├── AI Platform
├── Data Platform
└── Interoperability
```

The five top-level areas are logical architectural boundaries. They are not a claim about microservices, deployment units or technology choices.

## External Boundary

External systems may provide identity verification, interoperability, diagnostic or other healthcare-system exchange. Jano translates external representations at the Interoperability boundary and preserves internal ownership. Fayda is specifically external and does not become Jano's internal Person Identity authority.

## Stakeholders

Key stakeholder classes include patients, clinicians, nurses, diagnostics personnel, pharmacy personnel, facility administrators, health-system operators, integration partners, clinical governance actors and technical operators. Exact organizational accountability is governed separately.

## Boundary Rules

- External data does not become authoritative internal truth without governed interpretation.
- Internal clinical domains own clinical meaning.
- AI is a supporting capability.
- Data Platform is downstream for analytical and secondary use.
- Anchor is not part of this landscape.

## Open Questions

External system inventory, counterpart contracts, regulatory obligations, and facility-specific deployment topology require later evidence.

## Status
Draft for Architectural Review.
