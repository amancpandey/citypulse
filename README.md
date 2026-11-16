# CityPulse

**Your city. At a glance.**  
A city-wise data intelligence platform that collects public, permitted data; preserves provenance and history; and turns it into dashboards, statistical insights, ML predictions, and evidence-backed AI explanations.

## Product boundaries (v1)
- India-first; country-independent architecture.
- Multiple supported cities, one selected city at a time.
- No city-to-city comparisons, rankings, or leaderboards in v1.
- Eight long-term domains: weather & climate, environment, transport & mobility, economy & cost of living, civic infrastructure, news & local developments, population & public statistics, lifestyle & local activity.
- Initial MVP: weather + AQI + historical observations + source/freshness display.
- Never fabricate missing data. Show unavailable/stale/estimated status explicitly.
- Distinguish observations, forecasts, official published statistics, and derived calculations.

## Architecture
Start as a modular monolith:
- `backend/`: FastAPI, SQLAlchemy, Alembic, PostgreSQL/PostGIS, Redis, Celery.
- `frontend/`: Next.js + TypeScript.
- Ingestion connectors normalize external providers into a common observation contract.
- Statistical calculations happen in backend services. ML models are separately versioned/evaluated.
- LLMs explain verified facts; they do not invent or calculate authoritative metrics.

## Local setup (planned)
1. Copy `backend/.env.example` to `backend/.env`.
2. Start dependencies: `docker compose up -d db redis`.
3. Create a Python virtual environment in `backend/`.
4. Install backend dependencies from `backend/requirements.txt`.
5. Run migrations and start the API (commands will be finalized in the first implementation slice).
6. Start the frontend from `frontend/` after its scaffold is generated.

## First vertical slice
One selected Indian city → weather and AQI ingestion → normalized observations → historical storage → city overview + charts → source and last-updated timestamp.

## Documentation
- `docs/PRODUCT_REQUIREMENTS.md`
- `docs/ROADMAP.md`
- `docs/ARCHITECTURE.md`
- `docs/DATA_GOVERNANCE.md`
- `docs/API_CONTRACTS.md`
- `docs/DECISIONS.md`

## Initial stack
Python 3.12+, FastAPI, PostgreSQL + PostGIS, SQLAlchemy 2, Alembic, Redis, Celery, HTTPX, Pydantic, Pandas, scikit-learn, Next.js, TypeScript, Recharts/ECharts, Docker Compose, Pytest, GitHub Actions.

## Status
Planning baseline. No provider integration, model, or feature should be marked complete until implemented and tested.
