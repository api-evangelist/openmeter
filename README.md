# OpenMeter (openmeter)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
