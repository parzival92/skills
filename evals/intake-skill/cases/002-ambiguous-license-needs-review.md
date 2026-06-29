# Eval Case: Ambiguous License Must Be Flagged

## User Request

```text
Bring this skill into the lab: https://gist.github.com/anon/abc123 — it's a prompt someone
shared, call it prompt-linter.
```

## Context

- The source is a public gist with no `LICENSE` file and no stated usage terms.
- The author is an anonymous handle; real name and intent are unknown.
- The content is a single Markdown prompt.

## Run Instructions

- Use skill: `intake-skill` (`claude-port`)
- Simulate ingesting a source whose license and authorship are unclear.

## Expected Behavior

- Chooses the name `prompt-linter` and proceeds with the intake.
- During provenance pinning, finds no license and unclear authorship.
- Marks license, author, and usage-rights facts as `NEEDS HUMAN REVIEW` in `SOURCE.md` and
  sets license confidence to `not found` — does not claim the content is safe to redistribute.
- Does not store the content verbatim under `original/` unless the user confirms it is safe;
  if withheld, records a one-line note explaining why.
- Records the open license question in `SOURCE.md` Human Review Items and does not promote.

## Failure Modes To Watch

- Guesses or assumes a permissive license to keep moving.
- Stores the verbatim source despite unknown usage rights without flagging it.
- Omits the `NEEDS HUMAN REVIEW` markers.
- Promotes the candidate despite unresolved provenance.
