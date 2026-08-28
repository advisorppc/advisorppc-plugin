# AdvisorPPC plugin for Claude Code

Work on your real ad accounts from Claude Code. This plugin connects Claude Code to the hosted AdvisorPPC connector — audit Google Ads campaigns, pull performance reports across Google Ads, Google Analytics 4, and Search Console, inspect Google Tag Manager setups, and review YouTube channel stats. Paid plans unlock budget and campaign management.

- Homepage: https://advisorppc.com
- Docs: https://advisorppc.com/docs

## What you get

- **Remote MCP server** (`advisorppc`) — the hosted connector at `https://mcp.advisorppc.com/claude`. No local install, no API keys in config; authentication is browser OAuth on first use.
- **Skills** that teach Claude proven workflows:
  - `google-ads-audit` — structured account/campaign audits: baseline, wasted spend, search terms, recommendations, change history.
  - `ppc-reporting` — cross-platform performance reports over Ads, Analytics, Search Console, and YouTube.
  - `getting-connected` — first-run setup, plans and quotas, troubleshooting.

## Install

### From a marketplace you have added

```
claude plugin install advisorppc@advisorppc
```

### Adding this repo as a marketplace first

This repository is itself a Claude Code plugin marketplace, so you can point Claude Code straight at it:

```
claude plugin marketplace add AdvisorAGI/advisorppc-plugin
claude plugin install advisorppc@advisorppc
```

Or interactively inside Claude Code:

```
/plugin marketplace add AdvisorAGI/advisorppc-plugin
/plugin install advisorppc@advisorppc
```

## First run

1. Install the plugin and start a new Claude Code session.
2. Run `/mcp` — the `advisorppc` server appears; connecting it opens the OAuth sign-in in your browser.
3. Approve the connection, then link the Google account that has access to your ad accounts.
4. Ask Claude to list your accounts (it will call `ga_list_accessible_customers_tool`) to confirm everything works.

## Plans

- **Free**: 100 tool calls per month, read-only tools — enough for periodic audits and reports.
- **Paid**: write tools (budget and campaign management) and higher quotas. See https://advisorppc.com for plans.

## Troubleshooting

Opening `https://mcp.advisorppc.com/claude` directly in a browser returns **401 — this is expected**: it is an MCP endpoint, not a web page. For anything else, see the `getting-connected` skill bundled with this plugin, or the docs at https://advisorppc.com/docs.
