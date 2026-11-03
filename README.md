# Wansom Briefly — plugin & connector

Legal and regulatory intelligence across African markets, inside your AI assistant: new laws and regulations, regulator notices, enforcement actions and court outcomes, each linked to its full analysis on [Briefly](https://www.wansom.ai/briefly).

Everything runs on one public, read-only MCP server — no account or API key:

```
https://www.wansom.ai/api/mcp
```

## Install

### Claude Code (plugin)

```
/plugin marketplace add wansom-ai/briefly-plugin
/plugin install briefly@wansom
```

This connects the Briefly server and adds three skills:

| Command | What it does |
|---|---|
| *(automatic)* `briefly:research` | Claude uses Briefly whenever you ask what changed in a market or sector |
| `/briefly:market-brief Kenya [topic] [days]` | A forwardable legal & regulatory brief for one market |
| `/briefly:sector-scan fintech Kenya Nigeria Ghana` | One sector compared across markets (or `Africa` for all) |

### Claude.ai and Claude Desktop (connector)

Settings → Connectors → **Add custom connector** → name it *Wansom Briefly* and paste `https://www.wansom.ai/api/mcp`.

### ChatGPT

Settings → Apps & Connectors → Advanced → turn on **Developer mode**, then **Create** a connector with the URL above (no authentication). The server exposes the standard `search` and `fetch` tools ChatGPT uses for deep research, plus the richer Briefly tools.

### Cursor, VS Code, Windsurf and other MCP clients

Add a remote (Streamable HTTP) server:

```json
{
  "mcpServers": {
    "briefly": { "type": "http", "url": "https://www.wansom.ai/api/mcp" }
  }
}
```

## Tools

| Tool | Purpose |
|---|---|
| `search_briefly` | Search developments by subject, country (code, name or "Africa"), topic, legal/regulatory, up to 90 days |
| `get_briefly_article` | Read the full Briefly analysis of up to 5 items |
| `list_briefly_coverage` | Markets with recent items, and the topic codes |
| `search` / `fetch` | Standard tools for ChatGPT deep research and other clients that expect them |

Every tool returns Markdown for the model plus the same result as structured data.

## What it returns — and doesn't

- Only content already public on Briefly. The assistant reads the full analysis to answer accurately, but is instructed never to display it in full: it summarises and invites the reader to open the full analysis on Briefly. Premium analyses come back as a preview with a link to the full piece.
- No case-law or statute databases: Kenya Law, AfricanLII and the other LIIs ask not to be used as AI input, so items from them are never returned.
- No sign-in, read-only; requests are rate-limited.

## Repository layout

```
.claude-plugin/marketplace.json     marketplace "wansom"
plugins/briefly/
  .claude-plugin/plugin.json        plugin manifest
  .mcp.json                         the remote Briefly MCP server
  skills/research/                  automatic research skill
  skills/market-brief/              /briefly:market-brief
  skills/sector-scan/               /briefly:sector-scan
```

The server itself lives in Wansom's `staging/` app (`src/app/api/mcp/route.ts`, `src/lib/mcp/`).

Validate before publishing: `claude plugin validate . && claude plugin validate plugins/briefly`.

Support: law@wansom.ai

## License

The plugin files (manifest, skills, docs) are MIT-licensed — see [LICENSE](LICENSE). The Briefly service and its content remain Wansom's and are subject to the [Wansom terms of service](https://www.wansom.ai/terms-of-service).
