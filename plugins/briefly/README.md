# Wansom Briefly

Legal and regulatory intelligence across African markets, inside Claude: new laws and regulations, regulator notices, enforcement actions and court outcomes in Kenya, Nigeria, South Africa, Ghana, Uganda, Tanzania, Rwanda and 40+ other markets — each linked to its full analysis on [Briefly](https://www.wansom.ai/briefly).

## Install

```
/plugin marketplace add wansom/briefly-plugin
/plugin install briefly@wansom
```

The plugin connects Claude to Briefly's public, read-only MCP server (`https://www.wansom.ai/api/mcp`; no account or API key needed) and adds three skills:

- **research** (automatic) — Claude searches Briefly whenever you ask what changed in a market or sector, reads the most relevant analyses, and answers with every development linked to Briefly.
- **`/briefly:market-brief <country> [topic] [days]`** — a forwardable legal and regulatory brief for one market.
- **`/briefly:sector-scan <sector> [countries…|Africa]`** — one sector or topic compared across markets.

Claude reads Briefly's full analyses so its answers are accurate, but never displays them in full: it summarises and invites you to read the full analysis on Briefly through the link. Premium analyses come back as a preview, and nothing comes from case-law or statute databases.

Support: law@wansom.ai
