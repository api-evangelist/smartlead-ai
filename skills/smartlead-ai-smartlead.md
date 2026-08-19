---
name: Smartlead
description: Use when building cold email campaign automation, managing leads at scale, configuring email account rotation, tracking campaign performance, or integrating outreach workflows with CRMs and external tools via webhooks.
metadata:
    mintlify-proj: smartlead
    version: "1.0"
---

# Smartlead API Skill

## Product Summary

Smartlead is a cold email outreach platform with a REST API for automating campaign management, lead handling, email account rotation, and performance tracking. Agents use it to programmatically create campaigns, import leads, configure email sequences, manage sender accounts, and sync campaign events with external systems via webhooks.

**Key files and endpoints:**
- Base URL: `https://server.smartlead.ai/api/v1`
- Authentication: API key passed as query parameter (`?api_key=YOUR_KEY`)
- Core resources: campaigns, leads, email-accounts, sequences, webhooks, analytics
- Primary docs: https://api.smartlead.ai

## When to Use

Reach for this skill when:
- **Building campaign automation**: Creating, configuring, and launching cold email campaigns programmatically
- **Managing leads at scale**: Importing, segmenting, categorizing, and tracking prospect lists (up to 400 per request)
- **Configuring email accounts**: Adding SMTP/OAuth accounts, enabling warmup, managing sender rotation
- **Tracking performance**: Fetching campaign analytics, open/click/reply rates, bounce metrics
- **Syncing with external tools**: Setting up webhooks to push campaign events (replies, bounces, opens) to CRMs or databases
- **Automating sequences**: Creating multi-step email sequences with delays and personalization
- **Managing lead lifecycle**: Pausing, resuming, categorizing, or unsubscribing leads mid-campaign

## Quick Reference

### Authentication
```bash
# API key stored in environment variable
export SMARTLEAD_API_KEY="your_key_here"

# Pass as query parameter
curl "https://server.smartlead.ai/api/v1/campaigns/?api_key=$SMARTLEAD_API_KEY"
```

### Campaign Workflow
| Step | Endpoint | Purpose |
|------|----------|---------|
| Create | `POST /campaigns/create` | Initialize campaign |
| Add sequences | `POST /campaigns/{id}/sequences` | Define email steps |
| Link accounts | `POST /campaigns/{id}/email-accounts` | Assign senders |
| Import leads | `POST /campaigns/{id}/leads` | Add prospects (max 400/request) |
| Set schedule | `POST /campaigns/{id}/schedule` | Configure sending times |
| Activate | `PATCH /campaigns/{id}/status` | Start sending |

### Lead Import Fields
```json
{
  "email": "required",
  "first_name": "optional",
  "last_name": "optional",
  "company_name": "optional",
  "custom_fields": {
    "job_title": "any key-value pairs",
    "industry": "up to 200 per lead"
  }
}
```

### Email Account Setup
| Type | Endpoint | Notes |
|------|----------|-------|
| SMTP | `POST /email-accounts/save` | Requires host, port, credentials |
| OAuth | `POST /email-accounts/save` | Gmail/Outlook with tokens |
| Warmup | `POST /email-accounts/{id}/warmup-settings` | Enable gradual ramp-up |

### Webhook Event Types
- `EMAIL_SENT` — Email delivered
- `EMAIL_OPENED` — Lead opened email
- `EMAIL_CLICKED` — Lead clicked link
- `EMAIL_REPLIED` — Lead replied (most important)
- `EMAIL_BOUNCED` — Undeliverable
- `LEAD_UNSUBSCRIBED` — Opt-out

### Key Rate Limits
| Tier | Requests/Min | Requests/Hour |
|------|--------------|---------------|
| Standard | 60 | 1,000 |
| Pro | 120 | 3,000 |

## Decision Guidance

### When to Use Batch vs. Individual Requests
| Scenario | Approach | Why |
|----------|----------|-----|
| Importing 1,000 leads | Batch in groups of 400 | Single request per 400 leads; respects API limits |
| Updating one lead status | Individual request | Simpler, no batching overhead |
| Fetching campaign list | Single GET request | Cached response, infrequent changes |
| Monitoring replies in real-time | Webhooks | Zero API calls; instant notifications |
| Polling for updates every 30s | Webhooks instead | Avoids rate limits and unnecessary requests |

### When to Use SMTP vs. OAuth
| Choice | When | Tradeoff |
|--------|------|---------|
| SMTP | Custom domain, full control | Requires SMTP credentials, manual setup |
| OAuth (Gmail/Outlook) | Quick setup, less config | Limited to Gmail/Outlook, token refresh needed |

### Campaign Segmentation Strategy
| Structure | Use Case |
|-----------|----------|
| One campaign per ICP segment | Different personas, industries, or company sizes |
| One campaign per geography | Region-specific messaging |
| One campaign per test variant | A/B testing subject lines or copy |

## Workflow

### Typical Campaign Launch
1. **Verify API key**: Test connection with `GET /campaigns/` to confirm authentication
2. **Create campaign**: `POST /campaigns/create` with name and tracking settings
3. **Add sequences**: `POST /campaigns/{id}/sequences` with 3–4 emails, delays between 0–14 days
4. **Link email accounts**: `POST /campaigns/{id}/email-accounts` with 3–5 warmed accounts for rotation
5. **Validate leads**: Check for required fields (email, first_name) and custom field completeness
6. **Import leads**: `POST /campaigns/{id}/leads` in batches of 400, respecting block lists
7. **Configure schedule**: `POST /campaigns/{id}/schedule` with timezone, hours, daily limits
8. **Activate**: `PATCH /campaigns/{id}/status` with `{"status": "ACTIVE"}`
9. **Monitor**: Poll `GET /campaigns/{id}/analytics` or set up webhooks for real-time events

### Webhook Integration
1. **Create webhook endpoint**: HTTP POST handler that accepts JSON payloads
2. **Register webhook**: `POST /webhooks` with URL and event types
3. **Verify signature**: Check `X-Smartlead-Signature` header (HMAC-SHA256)
4. **Process events**: Parse payload, update CRM/database, return 200 OK
5. **Handle duplicates**: Webhooks may retry; idempotency is your responsibility

### Lead Management at Scale
1. **Prepare data**: Validate emails, deduplicate, enrich with custom fields
2. **Batch import**: Split into 400-lead chunks, add 1-second pause between batches
3. **Monitor import**: Check `added_count` and `skipped_count` in response
4. **Categorize**: Use `PATCH /leads/{id}/category` to tag hot leads
5. **Export results**: `GET /campaigns/{id}/leads/export` for reporting

## Common Gotchas

- **API key in source code**: Never hardcode keys. Use environment variables or secrets manager. Keys shown only once during generation.
- **Exceeding 400 leads per request**: Batch imports fail silently if you exceed the limit. Always split into chunks.
- **Missing DNS records before warmup**: SPF, DKIM, DMARC must be configured before enabling account warmup. Bad DNS actively harms reputation.
- **Warmup not enabled on new accounts**: New accounts need 14–30 days of warmup before adding to active campaigns. Skip this and deliverability tanks.
- **Polling instead of webhooks**: Polling every 30 seconds burns rate limit quota. Use webhooks for real-time events instead.
- **Ignoring bounce rate spikes**: Monitor bounce rates; if >5%, pause campaign and investigate. High bounces damage sender reputation.
- **Empty personalization fields**: If custom fields are missing, emails send with empty placeholders (e.g., "Hi {{first_name}},"). Validate before import.
- **Not respecting Retry-After header**: On 429 errors, check the `Retry-After` header. Ignoring it causes thundering herd problems.
- **Campaign status confusion**: DRAFT campaigns don't send. Must be ACTIVE. PAUSED stops sending but preserves state. STOPPED is permanent.
- **Duplicate leads across campaigns**: By default, SmartLead prevents the same email from being added twice to the same campaign. Use `ignore_duplicate_leads_in_other_campaign: true` only if intentional.

## Verification Checklist

Before submitting campaign automation or integration work:

- [ ] API key stored in environment variable, not hardcoded
- [ ] Campaign has at least one sequence with subject and body
- [ ] At least 3–5 email accounts linked and warmed (14+ days)
- [ ] All leads have valid email addresses; custom fields validated
- [ ] Schedule configured with timezone, hours, and daily limits
- [ ] Campaign status is ACTIVE (not DRAFT)
- [ ] Error handling in place for 400, 401, 404, 429, 500 errors
- [ ] Batch imports split into 400-lead chunks with pauses
- [ ] Webhook endpoint returns 200 OK and handles duplicate events
- [ ] Rate limiting implemented (client-side throttle or exponential backoff)
- [ ] Bounce rate monitored; alert threshold set (e.g., >5%)
- [ ] Analytics endpoint tested; metrics (sent, opened, replied) accessible

## Resources

**Comprehensive navigation**: https://api.smartlead.ai/llms.txt

**Critical pages**:
1. [Getting Started Guide](https://api.smartlead.ai/guides/getting-started) — Step-by-step campaign setup with code examples
2. [Error Handling Guide](https://api.smartlead.ai/guides/error-handling) — HTTP status codes, retry logic, common errors
3. [Best Practices Guide](https://api.smartlead.ai/guides/best-practices) — Deliverability, personalization, scaling, security patterns

---

> For additional documentation and navigation, see: https://api.smartlead.ai/llms.txt