# Smartlead (smartlead-ai)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Smartlead is cold email infrastructure for outbound sales and lead generation, focused on inbox deliverability through unlimited mailbox rotation, automated warmup, and a unified master inbox. Smartlead exposes a REST API at server.smartlead.ai/api/v1 covering campaigns, leads, email accounts, email warmup, webhooks, analytics, and client management, with API key authentication via query parameter.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/smartlead-ai/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/smartlead-ai/refs/heads/main/apis.yml)

## Tags

- Cold Email
- Outbound
- Sales
- Deliverability
- Email Warmup
- Automation
- Sequences

## Timestamps

- **Created:** 2026-05-23
- **Modified:** 2026-05-23

## APIs

### Smartlead Campaigns API

REST endpoints to create, list, fetch, update, schedule, pause, resume, and delete email campaigns, plus manage sequences, A/B variants, and sender account assignments inside a campaign.

- **Human URL:** [https://api.smartlead.ai/reference/campaigns](https://api.smartlead.ai/reference/campaigns)
- **Base URL:** `https://server.smartlead.ai/api/v1/campaigns`

#### Tags

- Campaigns
- Sequences
- Scheduling

#### Properties

- [Documentation](https://api.smartlead.ai/reference)
- [Postman Collection](collections/smartlead-ai.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/smartlead-ai.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Smartlead Leads API

Endpoints to add leads to a campaign in bulk, fetch leads, update lead status (interested, replied, unsubscribed), search leads globally, and manage lead categories.

- **Human URL:** [https://api.smartlead.ai/reference/leads](https://api.smartlead.ai/reference/leads)
- **Base URL:** `https://server.smartlead.ai/api/v1`

#### Tags

- Leads
- Contacts
- Prospects

#### Properties

- [Documentation](https://api.smartlead.ai/reference)
- [Postman Collection](collections/smartlead-ai.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/smartlead-ai.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Smartlead Email Accounts API

Endpoints to add, list, update, and remove sender mailboxes (SMTP, Gmail, Outlook), assign them to campaigns, and track per-account sending limits and warmup state.

- **Human URL:** [https://api.smartlead.ai/reference/email-accounts](https://api.smartlead.ai/reference/email-accounts)
- **Base URL:** `https://server.smartlead.ai/api/v1/email-accounts`

#### Tags

- Email Accounts
- SMTP
- Mailboxes

#### Properties

- [Documentation](https://api.smartlead.ai/reference)
- [Postman Collection](collections/smartlead-ai.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/smartlead-ai.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Smartlead Email Warmup API

Endpoints for managing Smartlead's deliverability warmup engine — enabling warmup per mailbox, configuring ramp settings, and reading warmup reputation and stats.

- **Human URL:** [https://api.smartlead.ai/reference/email-warmup](https://api.smartlead.ai/reference/email-warmup)
- **Base URL:** `https://server.smartlead.ai/api/v1/email-accounts`

#### Tags

- Warmup
- Deliverability
- Reputation

#### Properties

- [Documentation](https://api.smartlead.ai/reference)
- [Postman Collection](collections/smartlead-ai.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/smartlead-ai.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Smartlead Webhooks API

CRUD endpoints for campaign-scoped webhook subscriptions covering lead events (sent, opened, clicked, replied, bounced, unsubscribed) used to stream Smartlead activity to external systems.

- **Human URL:** [https://api.smartlead.ai/reference/webhooks](https://api.smartlead.ai/reference/webhooks)
- **Base URL:** `https://server.smartlead.ai/api/v1/webhooks`

#### Tags

- Webhooks
- Events
- Subscriptions

#### Properties

- [Documentation](https://api.smartlead.ai/reference)
- [Postman Collection](collections/smartlead-ai.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/smartlead-ai.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Smartlead Analytics API

Endpoints for campaign and account-level analytics — sent, open, click, reply, bounce, and unsubscribe metrics aggregated over time ranges.

- **Human URL:** [https://api.smartlead.ai/reference/analytics](https://api.smartlead.ai/reference/analytics)
- **Base URL:** `https://server.smartlead.ai/api/v1`

#### Tags

- Analytics
- Reporting
- Metrics

#### Properties

- [Documentation](https://api.smartlead.ai/reference)
- [Postman Collection](collections/smartlead-ai.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/smartlead-ai.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Smartlead Client Management API

Endpoints for agency users to provision and manage white-labeled client accounts, assign permissions, and meter usage across multiple end customers.

- **Human URL:** [https://api.smartlead.ai/reference/client-management](https://api.smartlead.ai/reference/client-management)
- **Base URL:** `https://server.smartlead.ai/api/v1`

#### Tags

- Clients
- Agency
- Multi-Tenant

#### Properties

- [Documentation](https://api.smartlead.ai/reference)
- [Postman Collection](collections/smartlead-ai.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/smartlead-ai.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://www.smartlead.ai)
- [App](https://app.smartlead.ai)
- [Documentation](https://api.smartlead.ai/reference)
- [API Reference](https://api.smartlead.ai/reference)
- [Getting Started](https://api.smartlead.ai)
- [Pricing](https://www.smartlead.ai/pricing)
- [Blog](https://www.smartlead.ai/blog)
- [Sign Up](https://app.smartlead.ai/signup)
- [Sign In](https://app.smartlead.ai/login)
- [Help](https://help.smartlead.ai)
- [Privacy Policy](https://www.smartlead.ai/privacy-policy)
- [Terms of Service](https://www.smartlead.ai/terms-of-service)
- [LinkedIn](https://www.linkedin.com/company/smartleadhq)
- [Twitter](https://x.com/smartlead_ai)
- [YouTube](https://www.youtube.com/@smartlead)
- [L L Ms Txt](https://api.smartlead.ai/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
