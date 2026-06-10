# Agent Instructions

This repo is a hybrid lab and library for LLM skills. Work conservatively: preserve provenance, keep experiments separate from promoted skills, and update durable project memory when repo rules or decisions change.

## Before Meaningful Work

Read these files first:

- `README.md`
- `MEMORY.md`
- `docs/conventions.md`
- `docs/promotion-checklist.md`

If the task is an external skill intake, also read:

- `prompts/intake-external-skill.md`
- `templates/lab-skill/SOURCE.md`
- `templates/lab-skill/notes.md`
- `templates/eval-case.md`

## Repo Rules

- Use `labs/skills/<skill-name>/` for copied, adapted, or experimental skills.
- Use `skills/codex/<skill-name>/` only for promoted Codex-compatible skills, and `skills/claude/<skill-name>/` only for promoted Claude Code-compatible skills. A skill may be promoted to one or both, independently.
- Every copied external skill must have a `SOURCE.md`.
- Store verbatim originals under `original/` only when license and size allow.
- Mark uncertain provenance, authorship, or license facts as `NEEDS HUMAN REVIEW`.
- Manual evals are Markdown scenarios, not a heavy framework.
- Every promoted skill needs at least two manual eval cases.
- Do not promote a skill unless it passes the promotion checklist.
- This repo is public. Keep secrets, private PII, absolute local paths, paid/private source text, and raw transcript dumps out of it. Follow "Public Repo Hygiene" in `docs/conventions.md` before every commit.

## Memory

Update `MEMORY.md` when work changes durable project context, including repo layout decisions, workflow rules, promotion criteria, naming conventions, or lessons that should persist across sessions.

Do not add transient command output, one-off status updates, or raw copied source to `MEMORY.md`.
