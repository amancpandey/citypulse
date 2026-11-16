# CityPulse — Roadmap

## Phase 0 — Project bootstrap
- Create repository, issue templates, branch protections and CI.
- Scaffold FastAPI + Next.js + PostgreSQL/PostGIS + Redis.
- Add environment configuration, logging, migrations and health checks.
- Write architecture decisions and provider research notes.

**Exit:** clean local bootstrap, passing lint/tests, documented setup.

## Phase 1 — Data foundation
- Cities, areas, categories, metrics, data sources and observations.
- Provider connector interface and normalized ingestion contract.
- Data validation, idempotency, ingestion logs and retries.
- Admin endpoints for job status and coverage.

**Exit:** a fixture provider can ingest repeatable observations without duplicates.

## Phase 2 — First live city slice
- Select initial city (decision pending).
- Verify weather and AQI sources, terms, cadence, geographic resolution and historical availability.
- Implement connectors and scheduled ingestion.
- Persist current and historical readings.

**Exit:** live data is traceable and can be independently checked against source.

## Phase 3 — User dashboard
- City overview, weather and AQI panels.
- Historical charts and time-range controls.
- Source, coverage, freshness and quality indicators.
- Empty/stale/error states.

**Exit:** end-to-end user journey works for selected city.

## Phase 4 — Domain expansion
- Add domains only after source and licensing assessment.
- Prioritize news and economy after source verification.
- Add transport, civic, population and lifestyle as reliable datasets become available.

## Phase 5 — ML intelligence
- Baselines, anomaly detection, forecast experiments and evaluation.
- Model registry/versioning, monitoring and drift checks.
- Prediction API and clear uncertainty labels.

## Phase 6 — AI intelligence
- News classification/summarization.
- RAG assistant over trusted observations, reports and articles.
- Constrained natural-language analytics.
- Citations and prompt-injection defenses.

## Phase 7 — Production readiness
- Performance, caching, security review, observability, backups, deployment, accessibility and documentation.
