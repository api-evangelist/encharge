# Encharge (encharge)

Encharge is a behavior-based marketing automation platform built for SaaS companies, with a visual flow builder, broadcasts, segments, lead scoring, A/B testing, and 50+ native integrations (HubSpot, Stripe, Salesforce, Facebook Ads, and more). The platform combines email marketing automation, user profiles, and product-event tracking to send targeted emails based on what users do (or do not do) in a SaaS product. Encharge exposes REST, Ingest, and Transactional Email APIs authenticated with an API token.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/encharge/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/encharge/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Email Marketing
- Marketing Automation
- Transactional Email
- SaaS
- Behavioral Email
- Customer Engagement

## Timestamps

- **Created:** 2026-05-11
- **Modified:** 2026-05-11

## APIs

### Encharge REST API

REST API (v1) for managing people, segments, tags, fields, flows, broadcasts, and events in Encharge. Authentication is via an API key passed as the token query parameter or X-Encharge-Token header.

- **Human URL:** [https://docs.encharge.io/api-documentation](https://docs.encharge.io/api-documentation)
- **Base URL:** `https://api.encharge.io/v1`

#### Tags

- Marketing Automation
- Email Marketing
- SaaS

#### Properties

- [Documentation](https://docs.encharge.io/api-documentation)
- [Developer  Documentation](https://docs.encharge.io)
- [Postman Collection](collections/encharge.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/encharge.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Encharge Transactional Email API

REST API for sending transactional emails through Encharge. Accepts JSON payloads at POST /v1/emails/send and authenticates via the same API token used by the core REST API.

- **Human URL:** [https://docs.encharge.io/transactional-email-api/overview](https://docs.encharge.io/transactional-email-api/overview)
- **Base URL:** `https://api.encharge.io/v1`

#### Tags

- Transactional Email
- Email

#### Properties

- [Documentation](https://docs.encharge.io/transactional-email-api/overview)
- [Authentication](https://docs.encharge.io/transactional-email-api/authentication)
- [Reference](https://docs.encharge.io/transactional-email-api/reference)
- [Postman Collection](collections/encharge.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/encharge.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Encharge Ingest API

Ingest API for streaming people and activity events into Encharge from backend systems. Posts JSON payloads to ingest.encharge.io/v1/ using the same API token.

- **Human URL:** [https://docs.encharge.io/getting-started/connecting-your-app-to-encharge/ingest-api](https://docs.encharge.io/getting-started/connecting-your-app-to-encharge/ingest-api)
- **Base URL:** `https://ingest.encharge.io/v1`

#### Tags

- Events
- Ingestion
- Customer Data

#### Properties

- [Documentation](https://docs.encharge.io/getting-started/connecting-your-app-to-encharge/ingest-api)
- [Postman Collection](collections/encharge.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/encharge.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/encharge)
- [Website](https://encharge.io)
- [Documentation](https://docs.encharge.io)
- [A P I  Documentation](https://docs.encharge.io/api-documentation)
- [Pricing](https://encharge.io/pricing)
- [Sign Up](https://app.encharge.io/signup)
- [A P I  Integration](https://encharge.io/integrations/api/)
- [L L Ms Txt](https://docs.encharge.io/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
