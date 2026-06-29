# Eval Case: Audit Flags Duplication And No-Ops

## User Request

```text
Run the writing-great-skills audit on labs/skills/changelog-writer/claude-port/SKILL.md
before I promote it.
```

## Context

- The target `SKILL.md` under audit contains:

  ```markdown
  ---
  name: changelog-writer
  description: Writes a changelog.
  ---

  # Changelog Writer

  Use this skill when the user wants a changelog from a git range.

  ## Workflow

  1. Read the commits in the given range.
  2. Group commits into Added, Changed, Fixed, and Removed.
  3. Write the changelog to CHANGELOG.md. Be thorough and make it look nice.

  ## Output Expectations

  - Group commits into Added, Changed, Fixed, and Removed.
  - Write the result to CHANGELOG.md.
  - Be thorough.
  ```

- No other files are referenced by the skill.

## Run Instructions

- Use skill: `writing-great-skills` (audit-pass, `claude-port`)
- Input: the target `SKILL.md` path above.
- Audit only; do not edit the target file.

## Expected Behavior

- Flags the `## Output Expectations` block as **duplication** (a blocker): it restates
  workflow steps 2 and 3. Fix: delete the block, fold anything behavioural into per-step
  completion criteria.
- Flags "Be thorough" and "make it look nice" as **no-ops**; proposes deletion or a stronger
  leading word.
- Flags step 3's completion criterion as not checkable / not exhaustive (no definition of a
  complete changelog).
- Optionally notes the model-invoked `description` is thin (no trigger phrasing) given the
  skill is model-invocable.
- Emits a findings report grouped by severity that maps onto the Craft / Quality bullets in
  `docs/promotion-checklist.md`, ending with a verdict that the skill does NOT pass the gate
  and naming the blocker(s).

## Failure Modes To Watch

- Edits the target file instead of reporting findings.
- Misses the Output Expectations duplication, or treats it as a nit rather than a blocker.
- Accepts "Be thorough" / "make it look nice" as real instructions.
- Produces prose praise instead of a structured, severity-grouped findings report.
