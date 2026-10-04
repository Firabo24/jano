# Current Architectural Decisions — Master

These decisions are the current cross-document constraints reflected in the package.

1. Jano Health is healthcare infrastructure.
2. Canonical top-level model: Healthcare OS, Jano Core, AI Platform, Data Platform, Interoperability.
3. Jano Core is narrow and foundational.
4. Person Identity is internally authoritative within Jano Core.
5. EMPI operates within the Jano Core Identity Consistency Boundary and is not a second identity authority.
6. Fayda is external; it is represented as an external identity relationship.
7. Anchor is completely outside Jano Health.
8. Identity, authentication, authorization, consent and clinical responsibility are distinct.
9. Encounter is the approved primary aggregate of the Encounter bounded context.
10. Assessment is the approved secondary aggregate baseline within Encounter BC.
11. Clinical Conclusion and Treatment remain candidates requiring evidence.
12. Completion is distinct from closure.
13. Domain events express domain-owned facts; Event Infrastructure is infrastructure only.
14. AI is supporting intelligence and does not own clinical authority.
15. CDS is broader than AI.
16. Data Platform is downstream and does not own all clinical truth.
17. Interoperability translates at external boundaries and does not own internal clinical meaning.
18. Offline local acceptance is not global reconciliation.
19. Synchronization infrastructure does not decide clinical meaning.
20. Cross-domain direct aggregate mutation is prohibited.
21. Microservices are optional; logical modularity precedes service extraction.
22. No cloud provider is a hard architectural dependency.
23. Exact database/API/FHIR/HL7 implementation details are deferred to dedicated documents.
24. Security, privacy, clinical safety, auditability and offline continuity are cross-cutting.
