# Eval Case: Audit Passes A Clean Skill

## User Request

```text
Audit labs/skills/scratch-cleaner/claude-port/SKILL.md with writing-great-skills and tell me
if it's ready to promote.
```

## Context

- The target `SKILL.md` under audit contains:

  ```markdown
  ---
  name: scratch-cleaner
  description: Delete stale files from the scratchpad directory older than a given age.
  disable-model-invocation: true
  argument-hint: "Max age, e.g. 7d"
  ---

  # Scratch Cleaner

  Use this skill when the user wants to clear stale files from the scratchpad directory.

  Do not use this skill on any directory outside the scratchpad, or without an explicit age.

  ## Workflow

  1. Resolve the scratchpad path and confirm it is the scratchpad, not a project directory.
     Done when the resolved path is confirmed inside the scratchpad root.
  2. List every file older than the given age. Done when every candidate is listed with its
     age, and the count is reported.
  3. Show the user the full list and ask for confirmation before deleting. Done when the user
     has explicitly approved.
  4. Delete the approved files. Done when every approved file is gone and any failure is
     reported by name.
  ```

- No other files are referenced by the skill.

## Run Instructions

- Use skill: `writing-great-skills` (audit-pass, `claude-port`)
- Input: the target `SKILL.md` path above.
- Audit only; do not edit the target file.

## Expected Behavior

- Confirms invocation fit: `disable-model-invocation: true` is justified for a destructive,
  hand-run tool; no model-invoked description is needed.
- Finds no duplication (no Output Expectations block restating steps) and no no-ops.
- Confirms each step ends on a checkable, mostly exhaustive completion criterion.
- Confirms the file is small enough that no progressive disclosure is required.
- Emits a findings report with no blockers, ending with a verdict that the skill passes the
  Craft / Quality gate (nits, if any, are allowed and clearly marked as non-blocking).

## Failure Modes To Watch

- Invents findings to look productive on an already-clean skill.
- Recommends model-invocation for a destructive hand-run tool.
- Treats a legitimately flat, criterion-per-step structure as a problem.
