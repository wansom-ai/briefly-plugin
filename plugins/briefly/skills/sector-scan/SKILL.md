---
name: sector-scan
description: Scan one sector or legal topic across several African markets with Wansom Briefly and compare what regulators and courts did in each, with every development linked to its Briefly analysis.
argument-hint: <sector or topic> [countries…|Africa]
disable-model-invocation: true
---

# Sector scan: $ARGUMENTS

Compare how one sector or legal topic moved across markets.

**Inputs.** The first argument is the sector or topic (e.g. `fintech`, `data protection`, `mining`, `competition`). Any further arguments are the markets (country names or codes); with none, or with `Africa`, scan all African markets. If no sector was given, ask for one and stop.

## Steps

1. With named markets: call `search_briefly` once per market (`jurisdiction` set, the sector as `query`, `days` 60, `limit` 10). Otherwise call it once with `jurisdiction: "Africa"`, `days` 60 and `limit` 20.
2. Read the most significant items (at most 10, in batches of 5) with `get_briefly_article`.
3. Note the markets where Briefly found nothing — that is a finding too, not a gap to fill from memory.

## Format

```
# <Sector> across <markets> — last 60 days

**Overview:** where activity is concentrated and the common direction (2–4 sentences).

| Market | Development | Authority / court | Date | Effect |
|---|---|---|---|---|
| Kenya | … ([Briefly](URL)) | … | … | … |

## By market
### <Market>
The key developments in a few sentences each, each linked to Briefly.

## Patterns and what to watch
- Shared themes, diverging approaches, upcoming deadlines named in the results.

## Sources on Briefly
- [Title](URL)
```

Use only facts from the Briefly results and copy the links exactly. Say "no developments found on Briefly" for a market with nothing.
