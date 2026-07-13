# Notes

## What This Skill Does

`teach` turns the current directory into a stateful teaching workspace. It guides an agent to teach a topic over multiple sessions by maintaining a mission, trusted resources, reference material, learning records, lessons, and teaching notes.

The core idea is that teaching should be grounded in the user's real reason for learning, backed by high-trust resources, and adjusted over time based on evidence of what the user understands.

## When It Seems Useful

- The user wants to learn a topic across multiple sessions.
- The learning path should adapt to what the user already knows.
- The user wants durable learning artifacts, not just chat answers.
- The topic benefits from references, lessons, exercises, and learning records.

## When It Should Not Be Used

- The user asks for a quick one-off explanation.
- The workspace is not intended to hold learning files.
- The topic requires expert instruction or safety-critical supervision without human oversight.
- The user does not want files created or maintained in the current directory.

## Adaptation Plan

- Keep the stateful teaching workspace model.
- Keep the mission-first rule.
- Keep the requirement to use trusted resources instead of unsupported parametric guesses.
- Adapt metadata to Codex skill conventions.
- Make file creation expectations explicit for Codex.
- Keep supporting format files next to the candidate `SKILL.md`.

## Promotion Status

- Claude port promoted to `skills/claude/teach/` on 2026-07-13 after the
  writing-great-skills audit pass. Findings fixed at promotion: orphaned
  `GLOSSARY-FORMAT.md` wired into `SKILL.md` (root `GLOSSARY.md` file, glossaries
  removed from `reference/*.html`), "Output Expectations" duplication block removed,
  lesson-scope rule single-homed in workflow step 6, step 10 given a checkable
  completion. Worked example: `skills/claude/teach/examples/first-run-and-continuation.md`.
- Codex port remains a lab candidate and has **not** received the 2026-07-13 audit
  fixes; re-sync it with the promoted claude `SKILL.md` before promoting.

## Test Notes

- Test first-run behavior when no `MISSION.md` exists.
- Test continuation behavior when mission, resources, and learning records already exist.
- Watch for over-writing learning records before the user demonstrates understanding.
- Watch for lessons that become too broad instead of teaching one tightly scoped thing.
