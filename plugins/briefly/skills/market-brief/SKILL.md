---
name: market-brief
description: Write a legal and regulatory brief for one market from Wansom Briefly — the most important new laws, regulator actions, enforcement and court outcomes of the last few weeks, each linked to its Briefly analysis.
argument-hint: <country> [topic] [days]
disable-model-invocation: true
---

# Market brief: $ARGUMENTS

Produce a briefing a lawyer or compliance lead could forward to a client.

**Inputs.** The first argument is the market (a country name or code, e.g. `Kenya` or `NG`). Anything after it is an optional subject (e.g. `data protection`, `banking`) and an optional number of days (default 30, at most 90). If no market was given, ask for one and stop.

## Steps

1. Call `search_briefly` with `jurisdiction` set to the market, the subject (if any) as `query`, `days` as given, and `limit` 20. Run it once with `kind: "regulatory"` and once with `kind: "legal"` when no subject narrows it.
2. Pick the 5–8 developments that matter most to businesses operating there — binding rules, enforcement and decisions over commentary — and read them with one or two `get_briefly_article` calls (up to 5 ids each).
3. If the market has nothing in the period, say so, check `list_briefly_coverage`, and offer a longer period.

## Format

```
# <Market> legal & regulatory brief — <period>

**In short:** 2–3 sentences on the overall direction.

## Regulatory actions
### <Authority>: <what happened> — <date>
What it requires or decided, who is affected, deadlines. ([Briefly](URL))

## Enforcement
…

## Courts
…

## What to watch
- Deadlines, consultations, pending decisions mentioned in the results.

## Sources on Briefly
- [Title](URL)
```

Leave out any section with nothing in it. Use only facts from the Briefly results, copy the links exactly, and mark premium items as "full analysis on Briefly".
