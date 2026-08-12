# Anonymetrics — Claude plugin

Query your **privacy-first web analytics** from [Anonymetrics](https://www.anonymetrics.io) directly in Claude: visitors, page views, traffic sources and real-time visitors, in natural language.

This plugin wraps the Anonymetrics MCP server (`https://mcp.anonymetrics.io`) and adds slash commands and a skill so Claude can answer your analytics questions with real data.

## What's inside

| Type | Name | What it does |
|------|------|--------------|
| Command | `/overview [site] [days]` | Summary of a site: visitors, pageviews, top sources & pages |
| Command | `/realtime [site]` | Visitors active in the last 5 minutes |
| Command | `/top [site] [dimension] [days]` | Top pages / referrers / countries / browsers… |
| Skill | `anonymetrics-web-analytics` | Auto-answers questions about your site's traffic |

All read-only and scoped to your organization.

## Setup

The plugin declares the Anonymetrics MCP server in `.mcp.json`. On first use, Claude connects to `https://mcp.anonymetrics.io` and you authorize with **OAuth** (a consent screen asks for your Anonymetrics API key — create one in **Dashboard → API keys**). Nothing to configure by hand.

Prefer a local (stdio) server instead of the remote connector? Install the package:

```bash
npx anonymetrics-mcp   # with ANONYMETRICS_API_KEY=anx_live_…
```

## Test locally

```bash
claude --plugin-dir ./anonymetrics-plugin
```

## Links

- Docs & API: <https://www.anonymetrics.io/api-docs>
- OpenAPI: <https://app.anonymetrics.io/api/v1/openapi.json>
- MCP server: <https://mcp.anonymetrics.io>

Built by [Monolit Digital](https://www.anonymetrics.io).
