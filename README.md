# Encharge

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

Encharge is a behavior-based marketing automation platform built for SaaS companies, with a visual flow builder, broadcasts, segments, lead scoring, A/B testing, native forms, custom objects, and 50+ native integrations (HubSpot, Stripe, Salesforce, Segment, Facebook Ads, and more). The platform combines email marketing automation, user profiles, and product-event tracking to send targeted emails based on what users do (or do not do) in a SaaS product. Encharge exposes three developer surfaces: a REST API of 69 operations covering people, person fields, segments, tags, broadcasts, email templates, sending domains, custom objects and event subscriptions, described by a published OpenAPI 3.0 definition; a prose-documented Transactional Email API; and an Ingest API for streaming people and product events from a backend. All three authenticate with the same account token, passed in the X-Encharge-Token header or a token query parameter, with OAuth 2 available for partner apps.

**Areas:** Email Marketing · Marketing Automation · Transactional Email · Software-as-a-Service · Behavioral Email · Customer Engagement · Customer Data · Webhook

## Encharge on APIs.io

Everything profiled for Encharge is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/encharge/](https://apis.io/providers/encharge/)** — or go straight to one of the APIs or properties below.

### APIs (15)

- [Encharge Transactional Email API](https://apis.io/apis/encharge/transactional-email-api/) — REST API for sending transactional emails through Encharge. Accepts JSON at POST /v1/emails/send with exactly one of template, html or text, returns 202…
- [Encharge Ingest API](https://apis.io/apis/encharge/ingest-api/) — Single-endpoint Ingest API for creating/updating people and submitting product events into Encharge from an application backend. POSTs JSON to…
- [Encharge Account API](https://apis.io/apis/encharge/encharge-account-api/) — The Account API from Encharge — 2 operation(s) for account information.
- [Encharge Broadcasts API](https://apis.io/apis/encharge/encharge-broadcasts-api/) — The Broadcasts API from Encharge — 1 operation(s) for sending broadcasts.
- [Encharge Custom Objects Schema API](https://apis.io/apis/encharge/encharge-customobjectsschema-api/) — The Custom Objects Schema API from Encharge — 10 operation(s) for defining object types, their fields, and the associations between them.
- [Encharge Folders API](https://apis.io/apis/encharge/encharge-folders-api/) — The Folders API from Encharge — 2 operation(s) for organizing assets into folders.
- [Encharge People API](https://apis.io/apis/encharge/encharge-people-api/) — The People API from Encharge — 5 operation(s) for creating, updating, reading, unsubscribing and archiving people.
- [Encharge Person Fields API](https://apis.io/apis/encharge/encharge-personfields-api/) — The Person Fields API from Encharge — 4 operation(s) for managing person fields.
- [Encharge Segments API](https://apis.io/apis/encharge/encharge-segments-api/) — The Segments API from Encharge — 4 operation(s) for dynamic segments.
- [Encharge Email Domain Settings API](https://apis.io/apis/encharge/encharge-settings-api/) — The email settings API from Encharge — 5 operation(s) for adding and verifying sending domains.
- [Encharge Tags API](https://apis.io/apis/encharge/encharge-tags-api/) — The Tags API from Encharge — 2 operation(s) for tagging and untagging people.
- [Encharge Tags Management API](https://apis.io/apis/encharge/encharge-tags-management-api/) — The Tags Management API from Encharge — 5 operation(s) for the account tag registry and tag counts.
- [Encharge Webhooks API](https://apis.io/apis/encharge/encharge-webhooks-api/) — The Webhooks API from Encharge — 2 operation(s) for creating and deleting event subscriptions against Encharge's event catalog.
- [Encharge Custom Objects API](https://apis.io/apis/encharge/encharge-custom-objects-api/) — The Custom Objects API from Encharge — 11 operation(s) for custom objects.
- [Encharge Email Templates API](https://apis.io/apis/encharge/encharge-email-templates-api/) — The Email Templates API from Encharge — 7 operation(s) for email templates.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Encharge Webhooks](https://apis.io/asyncapis/encharge/encharge-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [encharge](https://apis.io/servers/encharge/encharge/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Encharge Agentic Access](https://apis.io/agentic-access/encharge/encharge-agentic-access/)

#### Collections (9)

Postman and Open Collection request collections.

- [Encharge REST API](https://apis.io/collections/encharge/open-encharge/)
- [Encharge REST Account API](https://apis.io/collections/encharge/open-encharge-account-api/)
- [Encharge REST Account Events API](https://apis.io/collections/encharge/open-encharge-events-api/)
- [Encharge REST Account Fields API](https://apis.io/collections/encharge/open-encharge-fields-api/)
- [Encharge REST Account Ingest API](https://apis.io/collections/encharge/open-encharge-ingest-api/)
- [Encharge REST Account People API](https://apis.io/collections/encharge/open-encharge-people-api/)
- [Encharge REST Account Segments API](https://apis.io/collections/encharge/open-encharge-segments-api/)
- [Encharge REST Account Tags API](https://apis.io/collections/encharge/open-encharge-tags-api/)
- [Encharge REST Account Transactional Email API](https://apis.io/collections/encharge/open-encharge-transactional-email-api/)

#### Overlays (14)

OpenAPI overlays, including conversational phrasing for each operation.

- [Encharge Account Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-account-api-phrasing-overlay/)
- [Encharge Broadcasts Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-broadcasts-api-phrasing-overlay/)
- [Encharge Custom Objects Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-custom-objects-api-phrasing-overlay/)
- [Encharge Customobjectsschema Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-customobjectsschema-api-phrasing-overlay/)
- [Encharge Email Templates Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-email-templates-api-phrasing-overlay/)
- [Encharge Folders Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-folders-api-phrasing-overlay/)
- [Encharge Openapi Overlay](https://apis.io/overlays/encharge/encharge-openapi-overlay/)
- [Encharge People Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-people-api-phrasing-overlay/)
- [Encharge Personfields Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-personfields-api-phrasing-overlay/)
- [Encharge Segments Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-segments-api-phrasing-overlay/)
- [Encharge Settings Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-settings-api-phrasing-overlay/)
- [Encharge Tags Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-tags-api-phrasing-overlay/)
- [Encharge Tags Management Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-tags-management-api-phrasing-overlay/)
- [Encharge Webhooks Api Phrasing Overlay](https://apis.io/overlays/encharge/encharge-webhooks-api-phrasing-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Encharge Authentication](https://apis.io/security/encharge/encharge-authentication/)
- [Encharge Domain Security](https://apis.io/security/encharge/encharge-domain-security/)
- [Encharge Trust Center](https://apis.io/security/encharge/encharge-trust-center/)
- [Encharge Vulnerability Disclosure](https://apis.io/security/encharge/encharge-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Encharge Scopes](https://apis.io/scopes/encharge/encharge-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Encharge Plans Pricing](https://apis.io/plans/encharge/encharge-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Encharge Rate Limits](https://apis.io/rate-limits/encharge/encharge-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://encharge.io)
- [Documentation](https://docs.encharge.io)
- [Getting started](https://docs.encharge.io/getting-started/connecting-your-app-to-encharge)
- [API reference](https://app-encharge-resources.s3.amazonaws.com/redoc.html)
- [Pricing](https://encharge.io/pricing)
- [Sign up](https://app.encharge.io/signup)
- [Support](https://help.encharge.io)
- [Changelog](https://encharge.noorahq.com/changelog)
- [Blog](https://encharge.io/feed/)
- [Security](https://encharge.io/responsible-disclosure/)
- [Compliance](https://gdpr.encharge.io/)
- [Terms of service](https://encharge.io/terms-of-service/)
- [Privacy policy](https://encharge.io/privacy-policy/)

## API Evangelist rating

**Kin Score 67.3** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 52.7 |
| Contract governance | 4.5 |
| Operational transparency | 34.2 |
| Developer ergonomics | 61.3 |
| Access clarity | 78.9 |

**Agent readiness 36.5** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | documented (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | distinct |

**Regulatory alignment 45.1** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/encharge/](https://apis.io/providers/encharge/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Encharge: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/encharge/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
