# Domain Ownership Matrix

**Document category:** DDD & Domain  
**Status:** Draft for Architectural Review  
**Version:** v0.2.0

## Purpose
Record current ownership maturity without presenting every future clinical capability as an already approved bounded context.

## Ownership Maturity

| Area | Current maturity | Current authority | Notes |
|---|---|---|---|
| Person Identity / EMPI | Approved baseline | Jano Core Identity | Authoritative internal identity boundary |
| Consent | Approved baseline | Jano Core | Foundational governance meaning |
| Authorization foundations | Approved baseline | Jano Core | Model-agnostic foundation |
| Trust foundations | Approved baseline | Jano Core | Contextual governance concept |
| Audit/accountability | Approved baseline | Jano Core | Meaningful accountability representation |
| Event infrastructure | Approved baseline | Jano Core | Infrastructure only |
| Encounter | Approved baseline | Healthcare OS / Encounter BC | Primary aggregate approved |
| Assessment | Approved baseline | Encounter BC / Assessment Aggregate | Secondary aggregate baseline approved |
| Clinical Conclusion | Candidate | Encounter BC | Further invariant/lifecycle evidence required |
| Treatment | Candidate | Encounter BC | Further evidence required |
| Medication Management | Candidate/domain under review | Clinical domain owner | Do not infer final BC/aggregate model solely from current feature implementation |
| Laboratory | Candidate/domain under review | Clinical domain owner | Dedicated semantics require review |
| Radiology | Candidate/domain under review | Clinical domain owner | Dedicated semantics require review |
| Referral/Care Coordination | Candidate/domain under review | Clinical domain owner | Coordination ownership distinct from receiving Encounter |
| Scheduling | Candidate/domain under review | Clinical domain owner | Workflow existence does not itself establish BC |
| Emergency Triage | Capability/domain candidate | Clinical domain owner / Encounter for current MVP triage result | Current MVP triage result remains Encounter-owned |
| Longitudinal problem/condition | Candidate | Clinical domain owner | Distinct from encounter diagnosis |

## Rules

1. Approved means explicitly accepted in the architectural record.
2. Strong candidate means sufficient evidence for continued detailed modeling but not approval.
3. Candidate means boundary remains open.
4. Future/adjacent means outside current architecture authority.
5. A workflow is not automatically a bounded context.
6. A noun is not automatically an aggregate.
7. Data access does not transfer state ownership.

## Status
Draft for Architectural Review.
