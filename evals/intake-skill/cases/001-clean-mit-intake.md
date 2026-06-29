# Eval Case: Clean MIT External Skill Intake

## User Request

```text
Intake the skill at https://github.com/someone/skills/tree/main/skills/git/branch-cleaner
into the lab.
```

## Context

- The source repo declares an MIT `LICENSE` with a clear copyright holder.
- The source path contains `SKILL.md` and one `README.md`, both small.
- No existing `labs/skills/branch-cleaner/` directory.

## Run Instructions

- Use skill: `intake-skill` (`claude-port`)
- Simulate ingesting the external skill into `labs/skills/branch-cleaner/`.

## Expected Behavior

- Chooses the kebab-case name `branch-cleaner` and confirms nothing is overwritten.
- Pins provenance before copying: confirms MIT + copyright holder, resolves the latest commit
  SHA touching the path, and enumerates the two source files.
- Stores verbatim `original/SKILL.md`, `original/README.md`, and `original/LICENSE`.
- Writes `SOURCE.md` with the pinned commit SHA, pinned source URL, license, and license
  confidence `confirmed` — no blank required fields.
- Writes `notes.md` with all four sections filled.
- Drafts at least one runtime port under `claude-port/` and/or `codex-port/`, with frontmatter
  matching the runtime rules.
- Scaffolds two `evals/branch-cleaner/cases/` files with matching `expected/` files.
- Ends with a promotion-readiness summary and writes nothing under `skills/codex/` or
  `skills/claude/`.

## Failure Modes To Watch

- Copies files before pinning the commit / confirming the license.
- Invents a commit SHA or license terms instead of resolving them.
- Promotes directly into a published runtime folder.
- Leaves `SOURCE.md` required fields blank or fabricates them.
