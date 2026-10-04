# Review Guidance — Canonical Authority

The 20 files under `01_CANONICAL_BASELINE/` are the authoritative approved architecture. Draft documents must be reviewed against them and may not silently override them.

# Review Guidance — Updated

## For every document
Ask: Who owns the meaning? What state is authoritative? What are the invariants? What lifecycle/correction semantics apply? What depends on it? What does it depend on? What happens offline? What is the security/privacy/safety boundary? What evidence is required for approval?

## DDD review
Do not approve an aggregate because it is a noun, has a separate UI, is safety-sensitive, or is convenient. Require independent authority, invariant family, lifecycle/correction semantics and justified coordination/consistency boundaries.

## Identity review
Keep Representation, Person, Patient Relationship and Identity Equivalence Decision distinct. Candidate is not confirmed truth. Reconciliation establishes governed relationships; identity does not directly mutate clinical aggregates.

## Event review
Keep event semantics separate from infrastructure delivery. Domain events belong to their semantic owner. AI-specific support events do not make AI owner of clinical domain meaning.

## Offline review
Distinguish local acceptance, pending propagation, global reconciliation, conflict and authoritative clinical truth. Do not let synchronization choose clinical meaning.

## AI/CDS review
Separate AI capability from CDS authority. Require human review where applicable, provenance, failure handling, safety evaluation and explicit non-autonomous boundaries.

## Governance/operations review
Look for decision authority, triggers, prerequisites, safeguards, recovery, escalation, evidence and change control.

## External reference review
Startup/EAII/IP references are factual supporting material and must not be used as architecture authority.
