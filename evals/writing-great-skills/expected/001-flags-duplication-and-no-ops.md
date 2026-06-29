# Expected Behavior: Audit Flags Duplication And No-Ops

A good run audits the file without modifying it and returns a structured findings report,
not prose praise.

The report must contain, at minimum:

- A **blocker** for the `## Output Expectations` block duplicating workflow steps 2–3, with
  the fix being deletion and folding any behavioural remainder into per-step completion
  criteria (single source of truth).
- At least one **no-op** finding covering "Be thorough" and "make it look nice", proposing
  deletion or a stronger leading word.
- A **completion-criterion** finding on step 3 (no checkable, exhaustive definition of done).

Each finding names a location, states the problem in one line, and gives a concrete fix.
The report is grouped by severity (blockers first) and ends with a one-line verdict that the
skill does not pass the Craft / Quality gate, naming the smallest set of blockers that would.

The findings map onto the Craft / Quality bullets in `docs/promotion-checklist.md`. The run
must not edit `changelog-writer`'s `SKILL.md`.
