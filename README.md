# Smartlead (smartlead-ai)

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
