# Project Memory

This file stores durable repo decisions and lessons. It is curated project memory, not a transcript log.

## Decisions

- This repo is a hybrid lab and library for LLM skills.
- The repo supports both Codex and Claude Code `SKILL.md` formats as parallel canonical promoted formats, and should remain open to other LLM or agent formats later.
- External or copied skills start under `labs/skills/`, not source-branded folders.
- Lab skills get per-runtime port folders (`codex-port/`, `claude-port/`) as needed; not every skill needs both.
- Mature Codex-compatible skills are promoted into `skills/codex/`; mature Claude Code-compatible skills are promoted into `skills/claude/`. A skill can be promoted to one runtime without the other.
- Every copied external skill requires a `SOURCE.md`.
- Verbatim originals can be stored under `original/` when license and size allow; otherwise store links and notes only.
- Codex may fill metadata, notes, evals, and candidate ports automatically, but uncertain facts must be marked `NEEDS HUMAN REVIEW`.
- Promoted skills require at least two manual eval cases (shared across runtimes unless behavior genuinely diverges).
- This repo is public: secrets, private PII, local paths, and transcript dumps are banned per "Public Repo Hygiene" in `docs/conventions.md`. Personal learning context inside `experiments/` workspaces is explicitly accepted.
- Claude Code `SKILL.md` files may use extra frontmatter fields (e.g. `allowed-tools`, `disable-model-invocation`, `argument-hint`) that Codex ports should strip; see `docs/conventions.md`.

## Intake History

- `teach` was the first external skill ingested into the lab. It came from Matt Pocock's public `mattpocock/skills` repository under `skills/productivity/teach`, pinned to commit `2bf70051928429983de3b5718d277150926f8c89`.
- The `teach` intake established the working pattern: keep upstream files and license under `labs/skills/teach/original/`, keep adapted candidates under `labs/skills/teach/codex-port/` and `labs/skills/teach/claude-port/`, and keep manual evals under `evals/teach/`.
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
- Which skill formats beyond Codex and Claude Code should get first-class adapters later?
