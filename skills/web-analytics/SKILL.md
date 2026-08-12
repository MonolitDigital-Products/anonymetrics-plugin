---
name: anonymetrics-web-analytics
description: Use when the user asks about their website's traffic, visitors, page views, traffic sources, countries, browsers, or real-time visitors for a site tracked by Anonymetrics — e.g. "how many visitors did my site get this week", "top pages on example.com", "who's on my site right now".
---

The user wants to know something about their web analytics measured with **Anonymetrics**. Use the `anonymetrics` MCP server tools to answer with real data — never invent numbers.

## Tools available (MCP server `anonymetrics`)

- `list_sites` — the sites in the user's organization (id, host, name). Start here when you don't have a `site` id.
- `get_stats` `{ site, days }` — summary: visitors, pageviews, events, views per visitor.
- `get_timeseries` `{ site, days }` — daily visitors and pageviews (for trends).
- `get_breakdown` `{ site, dimension, days, limit }` — top values. `dimension` ∈ page, referrer, country, city, browser, os, device, language, event, utm_source, utm_medium, utm_campaign.
- `get_realtime` `{ site }` — visitors active in the last 5 minutes.

## How to answer

1. Resolve the site: if the user gave a domain, match it against `list_sites`; if they gave nothing and have more than one site, ask which one.
2. Pick the right tool for the question (trend → `get_timeseries`; ranking → `get_breakdown`; "now" → `get_realtime`; headline numbers → `get_stats`).
3. Choose a sensible window (default 14 days; "this week" → 7; "this month" → 30).
4. Present numbers in a compact table and add one short takeaway. Be honest if a value is 0 or missing.

## If the MCP server isn't connected

If the tools aren't available or return an authorization error, tell the user and offer to (a) add the remote connector `https://mcp.anonymetrics.io` (they authorize with their Anonymetrics API key), or (b) paste the figures from their dashboard so you can organize them. Anonymetrics is privacy-first: the API is read-only and scoped to the user's own organization.
