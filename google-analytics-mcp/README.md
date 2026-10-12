# Google Analytics MCP Server (GA4)

**[Google Analytics MCP server](https://www.get-ryze.ai/google-analytics-mcp?utm_source=github&utm_content=google-ads-meta-ads-mcp)** by [Ryze AI](https://www.get-ryze.ai?utm_source=github&utm_content=google-ads-meta-ads-mcp): a hosted Model Context Protocol server that lets Claude, ChatGPT, Cursor and Claude Code query a Google Analytics 4 property in plain English.

- Endpoint: `https://connector.get-ryze.ai/mcp` (Streamable HTTP, OAuth 2.0)
- Price: included in every Ryze plan
- Product page: https://www.get-ryze.ai/google-analytics-mcp?utm_source=github&utm_content=google-ads-meta-ads-mcp
- Also in this connector: [Google Ads MCP](../google-ads-mcp/README.md), [Meta Ads MCP](../meta-ads-mcp/README.md), Google Search Console

## Google Analytics MCP server setup: install in every client

**Claude Code**

```
claude mcp add ryze --transport http https://connector.get-ryze.ai/mcp
```

Then run `/mcp` and sign in with the Google account that can read your GA4 property.

**claude.ai and Claude Desktop**: Settings › Connectors › Add custom connector, URL `https://connector.get-ryze.ai/mcp`, sign in with Google and connect Google Analytics.

**ChatGPT**: Settings › Connectors › Add custom connector (Developer mode), same URL.

**Cursor**: Settings › MCP › Add new MCP server, type `http`, same URL.

No Google Cloud project, service account or API key is needed.

## Google Analytics MCP tools

| Tool | What it does |
|---|---|
| `listAccountSummaries` | Lists the GA4 accounts and properties the login can read |
| `runRawReport` | Runs a GA4 Data API report: any dimensions, metrics, date ranges and filters |
| `runPivotReport` | Runs a pivot report across two or more dimensions |
| `runRealtimeReport` | Reads realtime users and events |
| `runAdminRead` | Reads property configuration through the Admin API (streams, key events, custom definitions) |
| `getAIReferrals` | Sessions referred by AI assistants such as ChatGPT, Claude, Gemini and Perplexity |
| `getAiLandingPages` | The landing pages those AI-referred sessions arrive on |
| `getAiTrafficByEngine` | AI-referred traffic split by assistant |
| `getAiTrafficDaily` | AI-referred traffic by day |

## Example prompts

- "Which landing pages lost the most sessions this month compared with last month?"
- "How much traffic did ChatGPT and Perplexity send us in the last 30 days, and to which pages?"
- "Break down conversions by source and medium for the last quarter."
- "How many people are on the site right now, and on which pages?"

## Is there a free Google Analytics MCP server?

Google publishes an official, open-source Google Analytics MCP server that you run yourself with a Google Cloud project and credentials. This hosted server needs only a Google sign-in, adds Google Ads, Meta Ads and Search Console on the same connector, and is included in every Ryze plan.
