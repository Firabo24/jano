# CURRENT_ARCHITECTURAL_DECISIONS.md

## Approved decisions carried forward

1. Jano Health is healthcare infrastructure.
2. Healthcare OS is the clinical umbrella.
3. Jano Core is narrow and foundational.
4. Identity authority remains internal to Jano Core.
5. EMPI remains a capability inside the identity boundary.
6. Fayda is external.
7. Encounter remains the approved bounded context / primary aggregate baseline for its lifecycle.
8. Assessment remains the approved secondary aggregate baseline within Encounter.
9. Clinical Conclusion and Treatment remain maturity-limited candidates where not independently established.
10. Cross-aggregate direct mutation is prohibited.
11. Domain-event meaning belongs to the owning aggregate/bounded context.
12. Event infrastructure is infrastructure only.
13. Audit records are distinct from domain events.
14. Offline local state is distinct from globally reconciled state.
15. AI remains supporting intelligence, not clinical authority.
16. Data Platform remains downstream of domain-owned clinical truth.
17. Interoperability owns external boundary concerns, not internal clinical meaning.
18. Microservices are optional.
19. No cloud provider is mandatory.
20. Security, privacy, clinical safety, auditability, trust, and offline-first are cross-cutting.

## Maturity rule

Approved decisions are authoritative. Drafts may elaborate them but cannot silently override them. A change to an approved decision requires explicit architectural review and versioned change control.
