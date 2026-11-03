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

Tools: `legal_research`, `find_cases`, `kenya_cause_list`, `draft_document`, `review_document`, `search_vault`, `read_document`, `list_workspaces`. They only ever create new documents — nothing is deleted or changed.

Support: law@wansom.ai
