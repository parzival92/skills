# Notes

## What This Skill Does

Turns the manual external-skill intake flow (currently the copy-paste prompt in
`prompts/intake-external-skill.md`) into an ordered, model-invocable skill. It pins provenance
before copying anything, stores verbatim originals under `original/`, fills `SOURCE.md` and
`notes.md`, drafts the runtime port(s), scaffolds two eval cases, and stops short of promotion.

## When It Seems Useful

- Bringing any external skill, prompt, or repo into `labs/skills/` (e.g. the
  `writing-great-skills` intake done by hand on 2026-06-30 — its worked reference).
- Keeping intakes consistent: same provenance fields, same pinned-commit discipline, same
  `NEEDS HUMAN REVIEW` honesty every time.

## When It Should Not Be Used

- Promoting a candidate (use `promote-skill` / `docs/promotion-checklist.md`).
- Authoring an original skill with no external upstream — there is nothing to track.

## Adaptation Plan

- Model-invoked (no `disable-model-invocation`) so a request like "ingest this skill" triggers
  it; the description carries trigger phrasing per `writing-great-skills`. Revisit if the
  context-load cost of an always-loaded description is not worth the autonomous reach.
- Steps each carry a checkable completion criterion and there is no `Output Expectations`
  block, so the skill should pass its own Craft / Quality gate.

## Test Notes

- Two eval cases under `evals/intake-skill/`:
  - `001-clean-mit-intake` — a well-licensed MIT external skill; the run must pin the commit,
    store verbatim originals + LICENSE, fill SOURCE/notes, draft a port, scaffold evals, and
    NOT promote.
  - `002-ambiguous-license-needs-review` — a source with no clear license; the run must mark
    license facts `NEEDS HUMAN REVIEW`, refuse to claim the license is safe, and still not
    promote.
- Outstanding before promotion: a worked example and a manual run of both eval cases.
