# DATA_PLATFORM_ARCHITECTURE.md

**Version:** v0.1.0  
**Status:** Draft for Architectural Review
**Document Owner:** Jano Health Architecture
**Parent Architecture:** Jano Health / Data Platform

## 1. Purpose

Define Data Platform as a governed downstream capability for clinical data, events, analytics, research, and data governance.

## 2. Ownership

Clinical domains remain authoritative for clinical meaning. Data Platform is downstream and does not own all clinical truth.

## 3. Conceptual Flow

```text
Domain-Owned Clinical State / Events
        ↓
Governed Data Consumption
        ↓
Data Platform
        ├── Analytics
        ├── Reporting
        ├── Research
        └── Other Governed Data Uses
```

## 4. Data Governance

Purpose, scope, consent, authorization, provenance, lineage, retention, and de-identification where applicable constrain downstream use.

## 5. Event Data

Domain events are consumed as governed facts with domain meaning. Event infrastructure is not itself the clinical source of meaning.

## 6. Research

Research consumes governed datasets and must not silently become an owner of operational clinical state.

## 7. AI

AI may consume governed context/data through appropriate boundaries. Training and analytics use does not redefine the source clinical truth.

## 8. Identity

Identity relationships are consumed from Jano Core and EMPI; Data Platform does not become the identity authority.

## 9. Corrections

Clinical corrections remain owned by clinical domains. Data Platform must reflect governed downstream interpretation.

## 10. Offline

Data may arrive later from offline nodes. Late arrival does not change the semantic owner of the data.

## 11. Non-Goals

No warehouse/lakehouse/vector/graph database design, schema, ETL implementation, or cloud data service selection is finalized here.

## Final Status

**DRAFT v0.1.0 — formal architectural review pending.**


## Review Gate

This artifact remains a draft. Approval requires explicit architectural review, consistency with the canonical baseline, and resolution of material ownership, lifecycle, safety, security, offline and integration questions relevant to the subject.
