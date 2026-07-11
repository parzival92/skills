# Mode: deep

Tear one item down to the level where the user could defend it in a system-design round.

## Workflow

1. **Resolve the target.**
   - A number → that item in `digests/<today>.md` (fall back to the most recent digest).
   - A URL → use it directly.
   - A topic → WebSearch for the most primary, most recent authoritative source
     (official docs/blog, the actual paper, the original postmortem — not coverage of it)
     and confirm the pick with the user only if two candidates are genuinely distinct stories.
   Completion: one URL chosen.

2. **Fetch the full text** with WebFetch. For papers, fetch the abstract page and the
   HTML full text when available; if only the PDF exists, work from the abstract plus the
   best secondary write-up and say so. If the page is paywalled or fetch fails twice, find
   an alternative primary source before settling for summaries.
   Completion: you are working from actual page content, not search snippets.

3. **Write the deep dive** with these sections:
   - **Context** — where this sits in the ecosystem and what existed before.
   - **The problem** — what breaks or hurts without it, stated concretely.
   - **How it works** — the actual mechanism: architecture, data flow, algorithms,
     real numbers from the source. This is the longest section.
   - **Trade-offs & failure modes** — what it costs, when it's the wrong choice, how it fails.
   - **In production** — how an operator with this user's stack would adopt it, what to
     watch, migration/rollback concerns.
   - **Interview Q&A** — 5 questions with strong answers, senior-level: design decisions,
     trade-offs, "what would you do when X fails" — not definition trivia.
   Completion: every section present; "How it works" cites specifics from the fetched text.

4. **Persist.** Append the 5 Q&A to `qbank.md` (question, source url, date added,
   `last-drilled: never`). If the target came from a digest, mark that read-log line with
   ` | deep-dived`. If it was a new URL/topic, append it to `read-log.md` first.
   Completion: qbank grew by 5 and the read-log reflects the dive.
