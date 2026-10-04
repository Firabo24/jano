# MVP Scope and Boundaries

**Document category:** Product and Business  
**Status:** Draft for Architectural Review  
**Version:** v0.2.0

## Purpose
Define the current MVP scope as a controlled subset of Jano Health capabilities while avoiding premature commitment to a specific authorization model or future domain architecture.

## MVP Boundary

The current MVP foundation covers: patient identity context and EMPI concepts; encounter lifecycle; assessment; clinical documentation; diagnostic workflows represented by current product scope; medication-related workflows represented by current product scope; referral/care coordination; offline-first operation and synchronization; audit/accountability; authorization/access control foundations; clinical safety and CDS; AI-assisted workflows; interoperability foundations.

## Access-Control Language

This document intentionally uses broad terms: authorization, access control, workforce permissions, audit/accountability and governed operation. It does **not** select RBAC, ABAC, ReBAC, or another specific authorization model as the enterprise architectural standard. Detailed authorization architecture remains governed by the dedicated security/core documents.

## What MVP Does Not Claim

The MVP does not claim national-scale deployment, national clinical authority, a finalized bounded context for every future clinical capability, autonomous AI clinical action, a mandatory microservice topology, or a hard dependency on a specific cloud provider.

## Scope Decision Rule
A capability enters the MVP when its clinical/product value is clear, ownership can be bounded, required safety/security/offline semantics can be stated, and implementation evidence exists or is intentionally planned. Presence in an early feature list is not enough to establish architectural approval.

## Future Boundary
Future capabilities may include additional clinical specialties, public health, education, research, smart-facility and expanded analytics functions, but they remain outside the MVP authority until separately reviewed.

## Status
Draft for Architectural Review.
