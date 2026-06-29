# Promotion Checklist

Use this checklist before moving a lab skill from `labs/skills/<skill-name>/codex-port/` to
`skills/codex/<skill-name>/`, or from `labs/skills/<skill-name>/claude-port/` to
`skills/claude/<skill-name>/`. Run it once per target runtime; a skill can be promoted to
one runtime before the other.

## Required

- `SOURCE.md` exists and has no unresolved critical provenance gaps.
- `SKILL.md` exists and follows the target runtime's skill format (see `docs/conventions.md`
  for runtime-specific frontmatter notes).
- The skill has clear trigger guidance.
- The skill has clear "do not use" guidance.
- At least two realistic manual eval cases exist.
- Matching expected behavior notes exist for each eval case.
- At least one worked example exists.
- Any scripts or templates referenced by `SKILL.md` exist.
- The skill does not require hidden secrets or one-off local context.

## Craft / Quality

The Required checks confirm a skill is *complete and safe*. These confirm it is
*well-crafted* — predictable and token-efficient. Vocabulary is defined in
`labs/skills/writing-great-skills/` (intaken from Matt Pocock, MIT). Run the executable
audit-pass in `labs/skills/writing-great-skills/claude-port/SKILL.md` rather than checking
these by hand.

- Invocation choice is justified: `disable-model-invocation` is set when the skill only ever
  fires by hand; a model-invoked description is present only when the agent (or another
  skill) must reach it on its own.
- No duplication: each meaning lives in one place (single source of truth). In particular,
  an "Output Expectations" / summary block does not restate the workflow steps.
- No-ops removed: every line changes behaviour versus the model's default; weak instructions
  ("be thorough", "make it nice") are cut or replaced with a stronger leading word.
- Completion criteria are checkable: each step ends on a condition the agent can tell
  done-from-not-done, and is exhaustive where it matters (guards against premature
  completion).
- Leading words are exploited: restated triads/phrases are collapsed into a single
  pretrained concept where one exists.
- Progressive disclosure applied: reference only some branches need is pushed behind a
  context pointer; `SKILL.md` is not bloated (no sprawl/sediment).

## Recommended

- Run the eval cases manually after meaningful edits.
- Keep adaptation notes explaining what changed from the original.
- Leave unresolved uncertainty as `NEEDS HUMAN REVIEW` instead of guessing.
