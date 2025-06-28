# Startup Funding Companies

n8n automation that detects newly funded startups, enriches company data, and routes qualified leads to the sales pipeline for timely outreach.

## Workflow

<img width="1193" height="424" alt="Startup Funding Workflow" src="https://github.com/user-attachments/assets/b4d6868e-6e27-4ebc-b036-2d65bbe54cd2" />

## How It Works

```
Funding data source (Crunchbase / RSS feed)
  → Detect new funding round
  → Enrich company data (industry, size, tech stack)
  → Score lead fit against ICP
  → If qualified:
      → Create lead in CRM
      → Add to outreach sequence
      → Notify sales team
  → Log all events to Airtable
```

## Features

- **Real-time detection** — Monitors funding announcements as they happen
- **Auto-enrichment** — Pulls company size, industry, tech stack, and key contacts
- **ICP scoring** — Filters companies that match your ideal customer profile
- **CRM integration** — Automatically creates leads in Close/HubSpot
- **Outreach trigger** — Adds qualified leads to email sequences

## Setup

1. Import `Startup Funding (1).json` into your n8n instance
2. Configure data source credentials (Crunchbase API or RSS feed URL)
3. Configure CRM API credentials (Close or HubSpot)
4. Configure Airtable for logging
5. Set schedule (default: runs every 4 hours)

## Configuration

| Variable | Description |
|----------|-------------|
| `DATA_SOURCE_URL` | Funding data API or RSS feed |
| `CRM_API_KEY` | Close or HubSpot API key |
| `AIRTABLE_API_KEY` | Airtable personal access token |
| `AIRTABLE_BASE_ID` | Logging base ID |
| `MIN_FUNDING_AMOUNT` | Minimum funding to trigger (default: $1M) |
| `TARGET_INDUSTRIES` | Comma-separated list of target industries |

## ICP Criteria

| Criteria | Threshold |
|----------|-----------|
| Funding Amount | > $1M |
| Employee Count | 20-500 |
| Industry | SaaS, Fintech, E-commerce, MarTech |
| Region | US, EU, GCC |

## Metrics

Tracked in Airtable:
- Companies detected per day
- Qualification rate
- Leads created
- Outreach sequences triggered
