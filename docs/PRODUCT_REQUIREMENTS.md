# CityPulse — Product Requirements v1.0

## 1. Product vision
Help people understand what is happening in a selected city by unifying trustworthy public data, historical context, statistical analysis, machine-learning forecasts, and natural-language explanations.

## 2. Users and jobs
- Residents: check conditions and understand changes affecting daily life.
- Researchers/students: explore historical city indicators with traceable sources.
- Journalists/civic observers: find public indicators and local developments.
- Administrators: monitor provider health, ingestion, coverage, and data quality.

## 3. Product principles
1. Provenance first: every displayed value has a source and relevant timestamp.
2. No fabricated facts: missing data remains missing; stale data is labelled.
3. Granularity honesty: city, district, ward, neighborhood, and station readings must not be conflated.
4. Temporal honesty: preserve `observed_at`, `published_at` where applicable, and `collected_at`.
5. Explainability: distinguish raw observations, official statistics, forecasts, and derived values.
6. Modular delivery: build a reliable ingestion and historical-data foundation before adding many domains.

## 4. Geography and scope
- India-first, country-independent data model.
- Multiple cities are supported.
- User views one selected city at a time.
- City-to-city comparison, ranking, and leaderboard features are excluded from v1.

## 5. Domains (long-term product scope)
1. Weather & climate: current conditions, forecasts, rainfall, historical summaries.
2. Environment: AQI, PM2.5, PM10, pollutants, station coverage, available water/environment indicators.
3. Transport & mobility: transit information, disruptions, traffic and mobility indicators where permitted.
4. Economy & cost of living: fuel, essential commodities, rent/housing indicators, inflation and employment statistics.
5. Civic infrastructure: utilities, waste, projects, public services and complaint aggregates where accessible.
6. News & local developments: local news, official notices, projects, public events and incidents.
7. Population & public statistics: demographics, education, healthcare, employment and development indicators.
8. Lifestyle & local activity: tourism, attractions, events, cultural activity and public business information.

A domain is a roadmap commitment, not a promise that reliable city-level data exists for every metric or city.

## 6. MVP (P0)
- City search/selection and saved default city.
- City overview dashboard.
- Weather and AQI provider connectors for one initial city.
- Common metric/source/observation model.
- Historical observations stored without overwriting.
- Scheduled ingestion and retry handling.
- Type/unit/range/duplicate/freshness validation.
- Historical charts when sufficient data exists.
- Source attribution, geographic coverage, observed time, collection time, freshness.
- Admin view for ingestion runs and failures.
- Docker Compose, automated tests, CI.

## 7. ML requirements
ML is a later capability, not a prerequisite for the first data MVP.
- Forecast weather/AQI only when sufficient history and suitable labels are available.
- Anomaly detection for suspicious readings and unusual changes.
- Trend/seasonality detection for metrics with enough history.
- Record model version, training window, features, evaluation metrics, prediction time, target time and uncertainty where supported.
- Compare against simple baselines; do not ship a model that does not beat a reasonable baseline.
- Monitor drift and prediction error.
- Never present predictions as observations.

## 8. AI requirements
- City intelligence assistant answers questions using stored, source-attributed facts.
- Natural-language analytics maps user questions to a constrained set of approved metrics and backend queries.
- News classification and summarization may use NLP/LLMs.
- AI summaries cite the underlying metrics/articles and their timestamps.
- Backend computes all authoritative numbers; LLM explains results.
- Guard against prompt injection in retrieved news/web content.
- Log model/provider, prompt version, retrieved source IDs, and response metadata without storing unnecessary personal data.

## 9. Non-goals (v1)
- City comparisons/rankings.
- Social network or public user posts.
- Financial trading recommendations or personal finance account connections.
- Unsupported real-time tracking.
- Unverified scraping or violating source terms.
- AI-generated statistics without traceable source records.

## 10. Core entities
Users, Cities, CityAreas, Categories, Metrics, DataSources, SourceMetrics, Observations, Forecasts, IngestionJobs, DataQualityReports, AggregationRecords, NewsArticles, ModelVersions, Predictions, AlertRules, AlertEvents.

## 11. Observation contract
Minimum fields: `city_id`, optional `area_id`, `metric_id`, `source_id`, `value_numeric` or typed value, `unit`, `observed_at`, `collected_at`, `record_type`, `quality_status`, `geographic_granularity`, `raw_payload_ref`, and metadata.
Do not overwrite old observations. Corrected/revised source data should be represented with revision lineage.

## 12. Acceptance criteria
- User can select an Indian city.
- Weather and AQI are fetched from verified permitted providers.
- Values are normalized and stored historically.
- Scheduled jobs can retry and expose failures.
- Dashboard charts use persisted observations, not hardcoded demo values.
- Every displayed metric shows source, time and coverage.
- Missing/stale values are explicit.
- Docker Compose starts required dependencies.
- Core ingestion, normalization and API behavior has automated tests.
