# Domain Event Ownership Matrix

**Document category:** Current Architecture Draft  
**Status:** Draft for Architectural Review  
**Version:** v0.1.1

## Purpose
Clarify semantic ownership of domain events and prevent AI or infrastructure components from becoming accidental owners of clinical domain meaning.

## Ownership Rule
A domain event expressing an authoritative state change is owned by the aggregate/bounded context that owns that state. The owner defines the event's semantic meaning and governs changes to that meaning.

## Matrix

| Event class | Semantic owner | Infrastructure role | Status |
|---|---|---|---|
| Encounter lifecycle events | Encounter domain | Propagation/delivery | Approved event architecture |
| Assessment lifecycle/finding events | Assessment aggregate / Encounter BC | Propagation/delivery | Approved baseline |
| Identity domain events | Jano Core Identity boundary | Propagation/delivery | Approved foundation |
| Consent / authorization / trust events | Corresponding Jano Core foundation | Propagation/delivery | Baseline foundation |
| Audit/accountability representations | Jano Core accountability foundation | Distribution/storage support as governed | Approved audit baseline |
| Clinical-domain state events (future/candidate) | Owning clinical domain | Propagation/delivery | Candidate |
| AI lifecycle/support events | AI Platform | Propagation/delivery | AI-specific, not clinical authority |

## AI Boundary

AI may produce AI-specific lifecycle/support events such as request, completion, validation, review or failure representations. Those events do not make AI the owner of the underlying clinical state. A clinical recommendation accepted by a clinician is interpreted and recorded according to the owning clinical workflow/domain.

## Event Infrastructure
Core Event Infrastructure provides publication, routing, delivery, retry and duplicate-safe handling semantics. It does not own the meaning of the event.

## Prohibited Shortcut

```text
AI Event → Clinical Truth
```

is not a valid ownership rule. The correct pattern is: AI output → governed review/workflow → domain-owned command/state change → domain event.

## Status
Draft for Architectural Review.
