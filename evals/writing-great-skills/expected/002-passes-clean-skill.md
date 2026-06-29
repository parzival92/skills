# Expected Behavior: Audit Passes A Clean Skill

A good run recognises a well-crafted skill and does not manufacture findings.

The report should confirm:

- Invocation fit — `disable-model-invocation: true` is correct for a destructive, hand-run
  tool, and no model-invoked description is warranted.
- No duplication and no no-ops.
- Every step ends on a checkable completion criterion.
- The file needs no progressive disclosure given its size.

It ends with a verdict that the skill passes the Craft / Quality gate. Any nits must be
clearly marked non-blocking. The run must not edit `scratch-cleaner`'s `SKILL.md`, and must
not recommend model-invocation for a destructive hand-run tool or flag the flat
criterion-per-step structure as a defect.
