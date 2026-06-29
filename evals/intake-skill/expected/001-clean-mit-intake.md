# Expected Behavior: Clean MIT External Skill Intake

A good run pins provenance before touching any file. It confirms the MIT license and
copyright holder, resolves the latest commit SHA that touches the source path, and lists the
exact upstream files — none assumed.

It then creates `labs/skills/branch-cleaner/` with verbatim `original/SKILL.md`,
`original/README.md`, and `original/LICENSE`; a `SOURCE.md` whose required fields are all
filled (pinned commit SHA, pinned source URL, license, confidence `confirmed`); a `notes.md`
with all four sections; at least one drafted runtime port; and two `evals/branch-cleaner/`
case/expected pairs.

It must not write anything under `skills/codex/` or `skills/claude/`, and must end with a
promotion-readiness list (worked example + manual eval run still outstanding). No commit SHA,
URL, or license term may be fabricated.
