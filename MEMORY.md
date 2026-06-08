# Project Memory

This file stores durable repo decisions and lessons. It is curated project memory, not a transcript log.

## Decisions

- This repo is a hybrid lab and library for LLM skills.
- The repo is Codex-first today, but should remain open to other LLM or agent formats later.
- Codex `SKILL.md` packages are the canonical promoted format for now.
- External or copied skills start under `labs/skills/`, not source-branded folders.
- Mature Codex-compatible skills are promoted into `skills/codex/`.
- Every copied external skill requires a `SOURCE.md`.
- Verbatim originals can be stored under `original/` when license and size allow; otherwise store links and notes only.
- Codex may fill metadata, notes, evals, and candidate ports automatically, but uncertain facts must be marked `NEEDS HUMAN REVIEW`.
- Promoted skills require at least two manual eval cases.

## Intake History

- `teach` was the first external skill ingested into the lab. It came from Matt Pocock's public `mattpocock/skills` repository under `skills/productivity/teach`, pinned to commit `2bf70051928429983de3b5718d277150926f8c89`.
- The `teach` intake established the working pattern: keep upstream files and license under `labs/skills/teach/original/`, keep the adapted candidate under `labs/skills/teach/codex-port/`, and keep manual evals under `evals/teach/`.
- External skill intakes should pin the upstream commit hash before promotion if immutable provenance matters.

## Skill Test Workspaces

- The first live `teach` experiment uses `labs/skills/teach/experiments/cka-june-2026-workspace/` so learning files do not pollute the repo root.

## Promotion Gate

A lab skill can move into `skills/codex/` only after:

- `SKILL.md` exists and follows Codex skill format.
- At least two realistic manual eval cases exist.
- At least one worked example exists.
- The skill has clear "use when" and "do not use when" guidance.
- It has no hidden dependency on one repo, one person, or one secret.

## Open Questions

- How much automation should eventually exist for running evals?
- Which non-Codex skill formats should get first-class adapters later?
