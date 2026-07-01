# OpenMeter (openmeter)

OpenMeter is open-source usage metering and billing for AI and API products. It ingests usage events as CloudEvents, aggregates them through meters, answers usage queries, and turns that usage into entitlements, balances, grants, usage-driven notifications, and Stripe-backed billing. Available as an open-source project and as OpenMeter Cloud with a Bearer-token REST API at https://openmeter.cloud/api/v1.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/openmeter/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/openmeter/refs/heads/main/apis.yml)

## Tags

- Usage Metering
- Billing
- Entitlements
- CloudEvents
- Open Source
- AI

## Timestamps

- **Created:** 2026-07-01
- **Modified:** 2026-07-01

## APIs

### OpenMeter Events Ingestion API

Ingests single or batched usage events that follow the CloudEvents 1.0 specification (application/cloudevents+json and cloudevents-batch+json), and lists ingested events for debugging. Event id enables idempotent deduplication; subject attributes usage; data carries the metered payload.

- **Human URL:** [https://openmeter.io/docs/getting-started/ingestion](https://openmeter.io/docs/getting-started/ingestion)
- **Base URL:** `https://openmeter.cloud/api/v1`

#### Tags

- Events
- Ingestion
- CloudEvents

#### Properties

- [Documentation](https://openmeter.io/docs/getting-started/ingestion)
- [API Reference](https://openmeter.io/docs/api)
- [OpenAPI](openapi/openmeter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openmeter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openmeter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### OpenMeter Meters API

Create, list, get, and delete meters that aggregate CloudEvents by eventType using SUM, COUNT, UNIQUE_COUNT, AVG, MIN, or MAX, reading the metered value and group-by dimensions from event data via JSONPath.

- **Human URL:** [https://openmeter.io/docs/getting-started/meters](https://openmeter.io/docs/getting-started/meters)
- **Base URL:** `https://openmeter.cloud/api/v1`

#### Tags

- Meters
- Aggregation

#### Properties

- [Documentation](https://openmeter.io/docs/getting-started/meters)
- [OpenAPI](openapi/openmeter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openmeter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openmeter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### OpenMeter Usage Query API

Queries aggregated usage for a meter across a time range with MINUTE / HOUR / DAY windows, filtered and grouped by subject and custom groupBy dimensions, plus listing the subjects that have reported usage.

- **Human URL:** [https://openmeter.io/docs/getting-started/query-usage](https://openmeter.io/docs/getting-started/query-usage)
- **Base URL:** `https://openmeter.cloud/api/v1`

#### Tags

- Usage
- Query
- Analytics

#### Properties

- [Documentation](https://openmeter.io/docs/getting-started/query-usage)
- [OpenAPI](openapi/openmeter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openmeter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openmeter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### OpenMeter Subjects API

Upserts, lists, gets, and deletes subjects - the keys (users, customers, tenants) that events are attributed to and that entitlements are provisioned against, optionally mapped to a Stripe customer.

- **Human URL:** [https://openmeter.io/docs/getting-started/subjects](https://openmeter.io/docs/getting-started/subjects)
- **Base URL:** `https://openmeter.cloud/api/v1`

#### Tags

- Subjects
- Metering

#### Properties

- [Documentation](https://openmeter.io/docs/getting-started/subjects)
- [OpenAPI](openapi/openmeter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openmeter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openmeter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### OpenMeter Entitlements API

Creates and manages metered, boolean, and static entitlements per subject and returns the entitlement value - hasAccess plus current balance, usage, and overage - so applications can gate features and enforce usage limits in real time.

- **Human URL:** [https://openmeter.io/docs/entitlements/overview](https://openmeter.io/docs/entitlements/overview)
- **Base URL:** `https://openmeter.cloud/api/v1`

#### Tags

- Entitlements
- Balances
- Access Control

#### Properties

- [Documentation](https://openmeter.io/docs/entitlements/overview)
- [OpenAPI](openapi/openmeter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openmeter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openmeter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### OpenMeter Features API

Defines the features that entitlements attach to, optionally bound to a meter for metered entitlements; supports create, list, get, and archive.

- **Human URL:** [https://openmeter.io/docs/entitlements/features](https://openmeter.io/docs/entitlements/features)
- **Base URL:** `https://openmeter.cloud/api/v1`

#### Tags

- Features
- Catalog

#### Properties

- [Documentation](https://openmeter.io/docs/entitlements/features)
- [OpenAPI](openapi/openmeter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openmeter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openmeter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### OpenMeter Grants API

Issues, lists, and voids usage grants that top up a metered entitlement's balance, with priority-based burn-down, expiration, and recurrence for allowances and credits.

- **Human URL:** [https://openmeter.io/docs/entitlements/grants](https://openmeter.io/docs/entitlements/grants)
- **Base URL:** `https://openmeter.cloud/api/v1`

#### Tags

- Grants
- Balances
- Credits

#### Properties

- [Documentation](https://openmeter.io/docs/entitlements/grants)
- [OpenAPI](openapi/openmeter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openmeter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openmeter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### OpenMeter Notifications API

Manages webhook notification channels and rules (such as entitlement balance thresholds) and lists delivered notification events with per-channel delivery status, so systems react to usage as it happens.

- **Human URL:** [https://openmeter.io/docs/notifications/overview](https://openmeter.io/docs/notifications/overview)
- **Base URL:** `https://openmeter.cloud/api/v1`

#### Tags

- Notifications
- Webhooks
- Alerts

#### Properties

- [Documentation](https://openmeter.io/docs/notifications/overview)
- [OpenAPI](openapi/openmeter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openmeter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openmeter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### OpenMeter Billing and Plans API

Turns metered usage into revenue - product-catalog plans, customers, billing profiles, and invoices - with Stripe-backed invoicing and payment collection.

- **Human URL:** [https://openmeter.io/docs/billing/overview](https://openmeter.io/docs/billing/overview)
- **Base URL:** `https://openmeter.cloud/api/v1`

#### Tags

- Billing
- Plans
- Invoicing
- Stripe

#### Properties

- [Documentation](https://openmeter.io/docs/billing/overview)
- [OpenAPI](openapi/openmeter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/openmeter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openmeter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/openmeterio)
- [LinkedIn](https://www.linkedin.com/company/openmeter)
- [Website](https://openmeter.io/)
- [Documentation](https://openmeter.io/docs)
- [Plans](plans/openmeter-plans-pricing.yml)
- [Rate Limits](rate-limits/openmeter-rate-limits.yml)
- [Fin Ops](finops/openmeter-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
