# Architecture decision records

## ADR-001: Modular monolith
**Decision:** Start with a modular monolith.  
**Reason:** One developer, limited daily time and early-stage requirements do not justify distributed-system overhead.

## ADR-002: One selected city at a time
**Decision:** Support multiple cities but show one selected city at a time. No city comparison in v1.  
**Reason:** Keep the user journey and first release focused.

## ADR-003: Provenance-first data
**Decision:** Store source and temporal/geographic metadata with every observation.  
**Reason:** A number without provenance, timestamp and coverage can mislead.

## ADR-004: ML/AI after trustworthy data
**Decision:** Build reliable ingestion/history before forecasting and LLM features.  
**Reason:** Models and generated explanations are only as credible as their underlying data.
