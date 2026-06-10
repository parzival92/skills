# Source

## Summary

- Skill name: teach
- Source type: external skill repository
- Original author: Matt Pocock
- Source URL or path: https://github.com/mattpocock/skills/tree/main/skills/productivity/teach
- Source commit: `2bf70051928429983de3b5718d277150926f8c89`
- Pinned source URL: https://github.com/mattpocock/skills/tree/2bf70051928429983de3b5718d277150926f8c89/skills/productivity/teach
- Date copied: 2026-06-09
- License: MIT License
- License confidence: confirmed from repository `LICENSE`

## Provenance Notes

This skill was copied from the public `mattpocock/skills` GitHub repository, under `skills/productivity/teach`.

The upstream folder contained:

- `SKILL.md`
- `GLOSSARY-FORMAT.md`
- `LEARNING-RECORD-FORMAT.md`
- `MISSION-FORMAT.md`
- `RESOURCES-FORMAT.md`

The repository root declares MIT License with copyright `(c) 2026 Matt Pocock`.

The copied source is pinned to upstream commit `2bf70051928429983de3b5718d277150926f8c89`.

## Usage Rights

The repository license is MIT, which permits copying and modification as long as the copyright notice and permission notice are included in copies or substantial portions of the software.

This lab copy includes the upstream license in `original/LICENSE`.

## Changes Made

- Preserved the upstream files under `original/`.
- Drafted a Codex candidate under `codex-port/`.
- Removed upstream Claude-specific metadata from the candidate Codex port.
- Drafted a Claude Code candidate under `claude-port/`, reusing the condensed `codex-port/`
  content and restoring the upstream `disable-model-invocation` and `argument-hint`
  frontmatter fields.
- Added manual eval cases under `evals/teach/`.

## Human Review Items

- Decide whether the final promoted skill should keep the name `teach` or use a more specific name like `stateful-teacher`.
