# MetricRaven for Claude

[MetricRaven](https://metricraven.com) is privacy-friendly web analytics with revenue attribution. This plugin connects Claude to your MetricRaven account through MetricRaven's remote MCP server, so you can ask about your websites in plain language in Claude chat, Cowork and Claude Code:

- "Chart my visitors and revenue for the last 30 days."
- "Which channels brought the most revenue this month?"
- "Show my top pages by visitors this week."

## What's inside

- `.mcp.json`: the MetricRaven MCP server, `https://metricraven.com/api/mcp` (remote, HTTPS). It is the same server as the MetricRaven connector in Claude's directory, so if you have both you see one set of tools.
- `skills/get-started`: tells Claude which MetricRaven tools to use for charts, numbers, goals and funnels, the default period, and to ask before making any change.
- `assets/icon.png`: the listing icon.

The plugin contains no scripts, hooks or local servers. It runs nothing on your computer.

## Sign-in and permissions

The first time you use a MetricRaven tool, connect MetricRaven from the plugin's Connectors tab (or `/mcp` in Claude Code). Claude opens MetricRaven's sign-in (OAuth 2.1 with PKCE). You choose the access (read reports by default; visitor details and write access are optional) and which websites the connection can read. Disconnect any time on the API & MCP page in MetricRaven.

## Data

Your questions and the tool requests Claude makes (website, period, filters) go to MetricRaven at `https://metricraven.com/api/mcp`, and MetricRaven returns analytics for the websites you approved. The plugin sends data nowhere else and stores nothing itself. See the [privacy policy](https://metricraven.com/legal/privacy).

## Links

- Docs: https://metricraven.com/docs/mcp
- Privacy policy: https://metricraven.com/legal/privacy
- Terms: https://metricraven.com/legal/terms
- Support: support@metricraven.com

Published by Dual Ninja LLC. MIT License.
