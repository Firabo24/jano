# ARCHITECTURE_PACK_INDEX.md

## Canonical navigation

Jano Health architecture is organized into an approved canonical baseline, active drafts, expanded draft categories, package controls/review records, and legacy material.

### Canonical baseline

The 20 files under `01_CANONICAL_BASELINE/` are the authoritative approved architecture. They are the reference point for all drafts.

### Current drafts

The 19 files under `02_CURRENT_ARCHITECTURE_DRAFTS/` extend the architecture and remain Draft.

### Expanded categories

The remaining 141 active architecture artifacts are distributed across the dedicated category directories and remain Draft.

### Canonical principles

- Clinical domains own clinical meaning and authoritative state.
- Jano Core is narrow and foundational.
- Identity is distinct from authentication, authorization, consent, and clinical responsibility.
- EMPI operates inside the Jano Core identity boundary.
- Fayda is external.
- Encounter is the approved primary aggregate baseline.
- Assessment is the approved secondary aggregate baseline within Encounter.
- AI is supporting intelligence, not clinical authority.
- CDS is broader than AI.
- Data Platform is downstream of clinical truth.
- Interoperability owns external boundaries and translation.
- Domain events retain domain ownership of meaning.
- Event infrastructure is infrastructure only.
- Offline local state is not automatically globally reconciled state.
- Logical boundaries precede deployment boundaries.
- Microservices and cloud providers are not mandatory architectural commitments.
