# Data governance and source verification

Before integrating a source, document:
- Owner/provider and official source URL.
- API/feed documentation and authentication requirements.
- License, attribution and commercial-use conditions.
- Rate limits, quotas and caching/redistribution restrictions.
- Geographic granularity and station/area coverage.
- Update cadence, historical depth and timestamp semantics.
- Units, schema stability and known limitations.
- Outage behavior and fallback policy.

Candidate discovery starting points (not pre-approved integrations):
- Weather: https://open-meteo.com/
- Indian government datasets: https://data.gov.in/
- CPCB: https://cpcb.nic.in/
- World Bank indicators: https://data.worldbank.org/
- OpenStreetMap: https://www.openstreetmap.org/

A candidate is not approved until its actual terms and endpoint behavior have been checked. Never scrape behind authentication or bypass access controls. Never infer city-level values from state-level data without explicitly labelling the transformation and its limitations.
