# Promotion Checklist

Use this checklist before moving a lab skill from `labs/skills/<skill-name>/codex-port/` to `skills/codex/<skill-name>/`.

## Required

- `SOURCE.md` exists and has no unresolved critical provenance gaps.
- `SKILL.md` exists and follows Codex skill format.
- The skill has clear trigger guidance.
- The skill has clear "do not use" guidance.
- At least two realistic manual eval cases exist.
- Matching expected behavior notes exist for each eval case.
- At least one worked example exists.
- Any scripts or templates referenced by `SKILL.md` exist.
- The skill does not require hidden secrets or one-off local context.

## Recommended

- Run the eval cases manually after meaningful edits.
- Keep adaptation notes explaining what changed from the original.
- Leave unresolved uncertainty as `NEEDS HUMAN REVIEW` instead of guessing.
