# Wansom AI

Wansom AI's legal workspace inside Claude. Research African law with Wansom's own engine — the official legal information institutes searched, citations checked, every case and statute linked — look up Kenya cause lists, draft and review documents, and work with your Wansom Vault. Everything Claude does through Wansom is saved in a **From Claude** workspace you'll find in Wansom AI.

Requires a Wansom AI **Pro, Teams or Explorer** plan. The first time Claude uses it, you sign in with your Wansom account and click **Allow**; disconnect any time in Wansom AI → Account settings → Connected apps.

## Install

```
claude plugin marketplace add wansom-ai/briefly-plugin
claude plugin install wansom@wansom
```

(or inside Claude Code: `/plugin marketplace add wansom-ai/briefly-plugin`, then `/plugin install wansom@wansom`)

In Claude.ai or Claude Desktop, add a custom connector with `https://www.wansom.ai/api/mcp/wansom` instead.

## What you get

- **legal-research** (automatic) — Claude uses Wansom's research whenever you ask an African-law question.
- **`/wansom:draft <document type> [details]`** — a new document from Wansom's drafting engine, saved and editable in Wansom AI. Also covers reviewing a Vault document.
- **`/wansom:cause-list <court> <station> [dates]`** — who hears which matter, where and when.

If your question doesn't name the jurisdiction, Claude shows an in-chat selector (`choose_jurisdictions`): tick several for a comparative analysis; drafting takes exactly one. The country you're in is pre-selected. Press **Start research** (or **Start drafting**) and Wansom runs it straight away and shows the answer in the card — nothing to retype. A jurisdiction your question already names is used directly — you're never asked again. The first time, Claude asks permission to use the Wansom AI tools; choose **Always allow** to skip that next time.

Tools: `choose_jurisdictions`, `legal_research` (+ `get_research_result`), `find_cases`, `kenya_cause_list`, `draft_document` / `review_document` (+ `get_draft`), `search_vault`, `read_document`, `list_workspaces`. Long research and drafts that outlast the assistant's time limit keep running in Wansom and are fetched with the `get_…` tools. They only ever create new documents — nothing is deleted or changed.

Support: law@wansom.ai
