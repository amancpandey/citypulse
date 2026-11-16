# Initial API contracts (draft)

Base prefix: `/api/v1`

## Cities
- `GET /cities?query=` — search supported cities.
- `GET /cities/{city_id}` — city metadata and available coverage.
- `GET /cities/{city_id}/overview` — latest available overview metrics.

## Catalog
- `GET /categories`
- `GET /metrics?category_id=`
- `GET /cities/{city_id}/coverage`

## Observations
- `GET /cities/{city_id}/observations?metric_key=&from=&to=&granularity=`
- `GET /cities/{city_id}/metrics/{metric_key}/latest`

## Ingestion/admin
- `GET /admin/ingestion/jobs`
- `GET /admin/ingestion/jobs/{job_id}`
- `POST /admin/ingestion/jobs/{source_key}/run` (admin only)

## Contract rules
- Return value, unit, source, `observed_at`, `collected_at`, geographic granularity, quality status and record type.
- Use ISO-8601 timestamps.
- Return explicit `unavailable`, `stale`, or `degraded` status where appropriate.
- Pagination for collections; validate time windows and metric keys.
- Do not expose raw provider secrets or internal payloads publicly.
