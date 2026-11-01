# Smartlead

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

Smartlead is cold email infrastructure for outbound sales and lead generation, focused on inbox deliverability through unlimited mailbox rotation, automated warmup, and a unified master inbox. Smartlead publishes an OpenAPI 3.1.1 contract with 98 operations at server.smartlead.ai/api/v1 covering campaigns, sequences, leads and lead lists, sender mailboxes and warmup, the master inbox, webhooks, analytics, Smart Delivery placement testing, Smart Senders and agency client management, authenticated with an API key passed as a query parameter. It also ships an unusually forward agent surface for its size — an A2A agent card, a published Agent Skill, a remote documentation MCP server, llms.txt, and a first-party CLI — alongside a 13-event signed webhook catalog.

**Areas:** Cold Email · Outbound · Sales · Deliverability · Email Warm-up · Automation · Sequences · A2A

## Smartlead on APIs.io

Everything profiled for Smartlead is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/smartlead-ai/](https://apis.io/providers/smartlead-ai/)** — or go straight to one of the APIs or properties below.

### APIs (19)

- [Smartlead Campaigns API](https://apis.io/apis/smartlead-ai/campaigns-api/) — REST endpoints to create, list, fetch, update, schedule, pause, resume, and delete email campaigns, plus manage sequences, A/B variants, and sender account…
- [Smartlead Leads API](https://apis.io/apis/smartlead-ai/leads-api/) — Endpoints to add leads to a campaign in bulk, fetch leads, update lead status (interested, replied, unsubscribed), search leads globally, and manage lead…
- [Smartlead Email Accounts API](https://apis.io/apis/smartlead-ai/email-accounts-api/) — Endpoints to add, list, update, and remove sender mailboxes (SMTP, Gmail, Outlook), assign them to campaigns, and track per-account sending limits and…
- [Smartlead Email Warmup API](https://apis.io/apis/smartlead-ai/email-warmup-api/) — Endpoints for managing Smartlead's deliverability warmup engine — enabling warmup per mailbox, configuring ramp settings, and reading warmup reputation and…
- [Smartlead Webhooks API](https://apis.io/apis/smartlead-ai/webhooks-api/) — CRUD endpoints for user, client and campaign-scoped webhook subscriptions covering lead events (sent, opened, clicked, replied, bounced, unsubscribed) used…
- [Smartlead Analytics API](https://apis.io/apis/smartlead-ai/analytics-api/) — Endpoints for campaign and account-level analytics — sent, open, click, reply, bounce, and unsubscribe metrics aggregated over time ranges.
- [Smartlead Client Management API](https://apis.io/apis/smartlead-ai/client-management-api/) — Endpoints for agency users to provision and manage white-labeled client accounts, mint and revoke per-client API keys, and meter usage across multiple end…
- [Smartlead Campaign Statistics API](https://apis.io/apis/smartlead-ai/smartlead-ai-campaign-statistics-api/) — Retrieve campaign performance metrics.
- [Smartlead Campaigns API](https://apis.io/apis/smartlead-ai/smartlead-ai-campaigns-api/) — Manage Smartlead email campaigns.
- [SmartLead Documentation MCP Server](https://apis.io/apis/smartlead-ai/mcp-server/) — SmartLead's remote Model Context Protocol server. tools/list answers anonymously with three documentation tools (search, a read-only docs filesystem,…
- [Smartlead Analytics API](https://apis.io/apis/smartlead-ai/smartlead-ai-analytics-api/) — Global analytics and reporting across all campaigns
- [Smartlead Authentication API](https://apis.io/apis/smartlead-ai/smartlead-ai-authentication-api/) — User authentication and account management
- [Smartlead Email Accounts API](https://apis.io/apis/smartlead-ai/smartlead-ai-email-accounts-api/) — Configure and manage email sending accounts
- [Smartlead Leads API](https://apis.io/apis/smartlead-ai/smartlead-ai-leads-api/) — Manage leads and prospects across campaigns
- [Smartlead Master Inbox API](https://apis.io/apis/smartlead-ai/smartlead-ai-master-inbox-api/) — Unified inbox for all campaign communications
- [Smartlead Smart Delivery API](https://apis.io/apis/smartlead-ai/smartlead-ai-smart-delivery-api/) — Email deliverability testing and monitoring
- [Smartlead Smart Senders API](https://apis.io/apis/smartlead-ai/smartlead-ai-smart-senders-api/) — Automated email account provisioning marketplace
- [Smartlead Utilities API](https://apis.io/apis/smartlead-ai/smartlead-ai-utilities-api/) — Utility endpoints for various operations
- [Smartlead Webhooks API](https://apis.io/apis/smartlead-ai/smartlead-ai-webhooks-api/) — Configure webhooks for real-time event notifications

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Smartlead Ai Webhooks](https://apis.io/asyncapis/smartlead-ai/smartlead-ai-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [smart_lead_api](https://apis.io/servers/smartlead-ai/smart-lead-api/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Smartlead Ai Agentic Access](https://apis.io/agentic-access/smartlead-ai/smartlead-ai-agentic-access/)

#### Collections (3)

Postman and Open Collection request collections.

- [Smartlead API](https://apis.io/collections/smartlead-ai/open-smartlead-ai/)
- [Smartlead Campaign Statistics API](https://apis.io/collections/smartlead-ai/open-smartlead-ai-campaign-statistics-api/)
- [Smartlead Campaign Statistics Campaigns API](https://apis.io/collections/smartlead-ai/open-smartlead-ai-campaigns-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Smartlead Ai Openapi Overlay](https://apis.io/overlays/smartlead-ai/smartlead-ai-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Smartlead Ai Authentication](https://apis.io/security/smartlead-ai/smartlead-ai-authentication/)
- [Smartlead Ai Domain Security](https://apis.io/security/smartlead-ai/smartlead-ai-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Smartlead Ai Plans Pricing](https://apis.io/plans/smartlead-ai/smartlead-ai-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Smartlead Ai Rate Limits](https://apis.io/rate-limits/smartlead-ai/smartlead-ai-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Smartlead Ai Finops](https://apis.io/finops/smartlead-ai/smartlead-ai-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.smartlead.ai)
- [Documentation](https://api.smartlead.ai/introduction)
- [Getting started](https://api.smartlead.ai/quickstart)
- [API reference](https://api.smartlead.ai/api-reference)
- [Pricing](https://www.smartlead.ai/pricing)
- [Sign up](https://app.smartlead.ai/signup)
- [Support](https://help.smartlead.ai)
- [Blog](https://www.smartlead.ai/blog)
- [Compliance](https://www.smartlead.ai/dpa)
- [Terms of service](https://www.smartlead.ai/new-terms-and-conditions)
- [Privacy policy](https://www.smartlead.ai/privacy-policy)
- [GitHub](https://github.com/Smartlead-Public)

## API Evangelist rating

**Kin Score 59.5** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 58.9 |
| Contract governance | 4.5 |
| Operational transparency | 42.1 |
| Developer ergonomics | 71.4 |
| Access clarity | 77.6 |

**Agent readiness 39.6** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | flavored (partial credit) |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 29.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/smartlead-ai/](https://apis.io/providers/smartlead-ai/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Smartlead: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/smartlead-ai/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
