---
name: research
description: Answer questions about recent legal and regulatory developments in African markets (new laws and regulations, regulator notices and circulars, enforcement actions and fines, court outcomes) using Wansom Briefly, with every development linked to its Briefly analysis.
when_to_use: The user asks what changed, what is new, or what a regulator or court did in a country or sector — e.g. "any new data protection enforcement in Kenya?", "what has the CBN issued on fintech this month?", "recent competition rulings in South Africa".
---

# Briefly legal & regulatory research

Briefly is Wansom's legal and regulatory intelligence service, strongest across African jurisdictions. Use its tools — never your own memory — for any claim about a recent development.

## Tools

- `search_briefly` — find developments. Pass the subject as `query`; a country named in the query ("Kenya data protection") filters by that country. Optional filters: `jurisdiction` (code or name, or "Africa" for all African markets), `topic`, `kind` (`legal` / `regulatory` / `all`), `days` (up to 90, default 30), `limit`.
- `get_briefly_article` — read the full analysis of up to 5 items at once (pass the ids from `search_briefly`). It is for you to answer from, not to paste.
- `list_briefly_coverage` — which markets have recent items, and the topic codes. Use it when unsure whether a market is covered.

## Method

1. Search once with the user's subject and market. If results are thin, widen once: a longer period, broader words, or no topic filter.
2. For anything beyond a one-line answer, read the 3–5 most relevant results with one `get_briefly_article` call before writing.
3. Write only what the results say. If Briefly has nothing on the point, say so plainly and suggest how to search differently — do not fill the gap from memory.

## Answer format

- A two- or three-sentence overview first.
- Then headings by country or theme. For each development: the date, the authority or court, what it requires or decided, who is affected, and why it matters in practice.
- End with **What to watch**: deadlines, consultations closing, pending decisions — only those the results mention.
- Link every development inline to its Briefly analysis — `… ([Briefly](URL))` — copying the exact URL from the results, and add the original source link where one is given.
- Close with a **Sources on Briefly** list of every item used.
- **Never display an analysis in full.** Read it so your answer is right, then summarise in your own words — at most a sentence or two quoted — and invite the user to read the full analysis on Briefly, e.g. "Read the full analysis on Briefly ([link](URL))." This applies even if the user asks for the whole text: give the summary and the link.
- For items marked as a premium analysis, use the preview and send the user to Briefly for the full piece.

Call it legal and regulatory intelligence, not "news". Briefly does not provide case-law or statute databases; for the text of a judgment or Act, point the user to the official source.
