# Initial backlog

## Bootstrap
- [ ] Create repository `citypulse`.
- [ ] Add README, docs, license decision and contribution guide.
- [ ] Scaffold FastAPI application and health endpoint.
- [ ] Scaffold Next.js app with TypeScript.
- [ ] Configure Docker Compose and environment variables.
- [ ] Add Alembic and first migration.
- [ ] Add GitHub Actions.

## Data foundation
- [ ] Define City, CityArea, Category, Metric, DataSource, SourceMetric, Observation and IngestionJob models.
- [ ] Define immutable observation and idempotency strategy.
- [ ] Define provider connector protocol.
- [ ] Add fixture connector and ingestion tests.
- [ ] Add validation and freshness calculation.

## First live slice
- [ ] Decide first city.
- [ ] Verify weather provider terms and coverage.
- [ ] Verify AQI provider terms and station coverage.
- [ ] Implement weather connector.
- [ ] Implement AQI connector.
- [ ] Schedule ingestion.
- [ ] Build city overview and historical charts.
