# MetricRaven for Claude

The Claude plugin for [MetricRaven](https://metricraven.com), privacy-friendly web analytics with revenue
attribution: see which traffic actually pays. It connects Claude to your MetricRaven account through
MetricRaven's remote MCP server, so you can ask about your websites in plain language in Claude chat,
Cowork and Claude Code, and get answers and charts back:

- "Chart my visitors and revenue for the last 30 days."
- "Which channels brought the most revenue this month?"
- "Which referrers brought paying customers in the last 90 days?"
- "Show my top pages by visitors this week."

You need a MetricRaven account with a website: sign up at https://metricraven.com.

## Install

Claude Code, from a clone of this repository (for the current session):

```sh
git clone https://github.com/Dual-Ninja-LLC/metricraven-claude-plugin
claude --plugin-dir ./metricraven-claude-plugin
```

Without the plugin, you can add the same MCP server yourself:

```sh
claude mcp add --transport http metricraven https://metricraven.com/api/mcp
```

In Claude Desktop and claude.ai: **Customize → Connectors → + Add → Add custom connector**, name it
MetricRaven and paste `https://metricraven.com/api/mcp`. Setup for other clients (ChatGPT, Cursor,
VS Code, Codex) is in the [MCP docs](https://metricraven.com/docs/mcp).

## What's inside

- `.mcp.json`: the MetricRaven MCP server, `https://metricraven.com/api/mcp` (remote, Streamable HTTP over HTTPS). If you also added MetricRaven as a connector, it is the same server, so you see one set of tools.
- `skills/get-started`: tells Claude which MetricRaven tools to use for charts, numbers, goals and funnels, the default period, and to ask before making any change.
- `.claude-plugin/plugin.json`: the plugin manifest.

The plugin contains no scripts, hooks or local servers. It runs nothing on your computer.

## What you can ask about

Traffic, revenue and MRR by channel, referrer, campaign, page and country; goals, funnels and paths to
payment; realtime visitors; AI crawlers and AI visibility; search keywords, ad spend and page speed. The
full list of tools and their inputs is in the [tool reference](https://metricraven.com/docs/mcp-tools).

## Sign-in and permissions

The first time you use a MetricRaven tool, connect MetricRaven from the plugin's Connectors tab (or `/mcp` in Claude Code). Claude opens MetricRaven's sign-in (OAuth 2.1 with PKCE). You choose the access (read reports by default; visitor details and write access are optional) and which websites the connection can read. Write access adds websites, chart notes, alerts, funnels, segments and goals; the server never deletes anything or changes your team or billing. Disconnect any time on the API & MCP page in MetricRaven.

## Privacy

Your questions and the tool requests Claude makes (website, period, filters) go to MetricRaven at `https://metricraven.com/api/mcp`, and MetricRaven returns analytics for the websites you approved. Without visitor details access, reports never include names, emails or visitor IDs. The plugin sends data nowhere else and stores nothing itself. See the [privacy policy](https://metricraven.com/legal/privacy).

## Links

- Docs: https://metricraven.com/docs/mcp
- Tool reference: https://metricraven.com/docs/mcp-tools
- Dashboard and sign-up: https://metricraven.com
- Privacy policy: https://metricraven.com/legal/privacy
- Terms: https://metricraven.com/legal/terms
- Support: support@metricraven.com

## License

MIT. See [LICENSE](LICENSE). Published by Dual Ninja LLC.
