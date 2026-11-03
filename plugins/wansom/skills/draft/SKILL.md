---
name: draft
description: Draft a legal document with Wansom AI's drafting engine — contracts, letters, notices, pleadings, policies — saved as an editable document in Wansom AI.
argument-hint: <document type> [details]
disable-model-invocation: true
---

# Draft with Wansom AI: $ARGUMENTS

1. Work out the document type and the facts it needs: parties (names and roles), purpose, key terms (amounts, dates, duration, termination), governing law, and anything the user wants included or avoided.
2. If real facts are missing for a document that depends on them (an NDA, a sale agreement, a demand letter), ask the user for them in one short list. Only use placeholders like `[PARTY A NAME]` if the user says to.
3. Call `draft_document` with `document_type`, the full `instructions`, and `jurisdiction`. To save it into one of the user's existing matters, call `list_workspaces` first and pass that `workspace_id`.
4. Show the user a short summary of the draft (structure and key clauses — not the whole text unless they ask) and the link to open and edit it in Wansom AI.

To review an existing document instead, find it with `search_vault` and call `review_document` with its id and what to focus on; summarise the main risks and recommended changes and give the link to the saved review.
