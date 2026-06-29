# Source

## Summary

- Skill name: intake-skill
- Source type: other (internally authored)
- Original author: this repository (Skills Lab)
- Source URL or path: derived from `prompts/intake-external-skill.md` and `docs/conventions.md`
- Date copied: 2026-06-30
- License: same as this repository
- License confidence: confirmed (no external source to track)

## Provenance Notes

This skill was authored in-repo, not copied from an external source. It codifies the existing
`prompts/intake-external-skill.md` prompt and the rules in `AGENTS.md` /
`docs/conventions.md` into an ordered, model-invocable workflow.

Because there is no external upstream, there is no `original/` directory: this skill is its
own source of truth. The pipeline it automates was exercised manually on
`labs/skills/writing-great-skills/` on 2026-06-30, which is the worked reference for its steps.

## Usage Rights

Original work, so it carries this repository's license. Safe to store and modify freely.

## Changes Made

- Authored `claude-port/SKILL.md` and `codex-port/SKILL.md` (identical: the workflow needs no
  runtime-specific frontmatter, so both use minimal `name` + `description`).
- Added eval cases under `evals/intake-skill/`.

## Human Review Items

- Decide whether intake should stay model-invocable (current choice — fires on "intake/ingest
  this skill") or become user-invoked. Model-invocation pays context load for a description
  that is loaded every turn; the trade is letting a request trigger it without a typed name.
- The `claude-port` and `codex-port` are byte-identical. Confirm both are wanted, or keep one.
