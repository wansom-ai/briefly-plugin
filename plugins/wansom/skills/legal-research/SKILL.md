---
name: legal-research
description: Answer legal questions about African law (Kenya, Nigeria, South Africa, Uganda, Tanzania, Ghana and others) with Wansom AI's research — the official legal information institutes searched, citations checked, every case and statute linked.
when_to_use: The user asks a legal question about an African jurisdiction — the law on a point, what a case decided, which authorities apply, the latest decisions on a topic — e.g. "what is the Kenyan position on unfair dismissal during probation?", "what did the Supreme Court decide in the BBI case?".
---

# Legal research with Wansom AI

Wansom AI runs the research on its own systems, as the signed-in user, and returns a researched answer. Use it instead of your own knowledge for any statement about what the law is or what a court decided.

## Tools

- `legal_research` — the main tool: Wansom's full research engine, the same as in the Wansom app. Pass the full `question` (keep any case names or citations the user gave) and the `jurisdiction` (country name). Usually 30–90 seconds, with progress shown while it works. Returns Wansom's checked answer, the sources, and where it was saved in Wansom.
- If it returns `status: "in_progress"` (Wansom needed longer than the time limit): show the user the sources found so far, say plainly that the draft is not yet citation-checked, then call `get_research_result` with the `research_id` — again after about 30 seconds if it is still running — and present the final answer in place of the draft.
- `find_cases` — a quick list of matching judgments (title, neutral citation, court, date, link) and Acts, when the user only wants to find authorities.
- If the jurisdiction isn't clear from the question, ask before searching.

## Presenting the answer

- Present Wansom's answer faithfully. Keep every link exactly as given. Never add cases, holdings, sections or citations that are not in it, and never "fill in" a point it says was not found — say so instead and offer the search link.
- You may restructure or shorten it for the user, but don't change what the authorities say.
- End with the sources list and tell the user the research is saved in their **From Claude** workspace in Wansom AI (link given in the result).
- If a tool says the plan doesn't include this, tell the user it's available on Wansom Pro, Teams and Explorer.
