# TERMINOLOGY_KNOWLEDGE_ARCHITECTURE.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Healthcare OS / Jano Core / AI Platform / Data Platform

## 1. Purpose

Define how shared clinical terminology and knowledge concepts are governed without inventing a new top-level domain.

## 2. Scope

Terminology, identity of concepts, mappings, version awareness, knowledge provenance, and controlled use of clinical vocabularies.

## 3. Ownership Principle

Clinical domains own clinical meaning. Shared terminology can support consistent representation but must not redefine domain authority.

## 4. Standard Concepts

FHIR/HL7 terminology representations and clinical coding systems may be integrated where relevant; exact profiles and code systems remain deferred.

## 5. Versioning

Terminology and knowledge changes must preserve version/provenance semantics so historical clinical meaning remains explainable.

## 6. AI Relationship

Knowledge resources may support CDS/AI, but knowledge retrieval does not make AI the clinical authority.

## 7. Offline

Approved terminology/knowledge may be available locally for constrained contexts. Local availability does not eliminate governance/version control.

## 8. Data Platform

Data Platform may use governed terminology for analytics and research, without taking ownership of the underlying clinical meaning.

## 9. Boundary

This remains a supporting capability rather than a new top-level Jano Health architecture domain.

## 10. Non-Goals

No terminology server, exact code-system inventory, ontology graph schema, RAG implementation, or API contract is finalized here.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
