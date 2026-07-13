---
name: teach
description: Teach the user a new skill or concept over multiple sessions using the current directory as a stateful teaching workspace.
disable-model-invocation: true
argument-hint: "What would you like to learn about?"
---

# Teach

Use this skill when the user wants to learn a topic, concept, or practical skill over multiple sessions and wants the current directory to hold durable learning state.

Do not use this skill for a quick one-off explanation, a task that should not create files, or a safety-critical learning domain that requires expert human supervision.

## Teaching Workspace

Treat the current directory as a teaching workspace. The learning state should be captured in these files and directories:

- `MISSION.md`: why the user is learning this topic. Use `MISSION-FORMAT.md`.
- `RESOURCES.md`: high-trust resources and communities. Use `RESOURCES-FORMAT.md`.
- `GLOSSARY.md`: canonical terminology for the workspace, added only as terms are genuinely understood. Use `GLOSSARY-FORMAT.md`.
- `reference/*.html`: compact reference documents, cheat sheets, algorithms, syntax guides, routines, or similar reusable learning artifacts.
- `learning-records/*.md`: durable records of demonstrated understanding, prior knowledge, corrected misconceptions, or mission shifts. Use `LEARNING-RECORD-FORMAT.md`.
- `lessons/*.html`: self-contained, printable lessons.
- `NOTES.md`: teaching preferences and working notes.

Create directories lazily when they are first needed.

## Workflow

1. Inspect the teaching workspace for existing `MISSION.md`, `RESOURCES.md`, `GLOSSARY.md`, `learning-records/`, `reference/`, `lessons/`, and `NOTES.md`.
2. If `MISSION.md` is missing or vague, interview the user before teaching. Establish the real-world outcome, success criteria, constraints, and out-of-scope topics.
3. If `RESOURCES.md` is missing or weak, gather high-trust resources before making factual claims. Prefer primary sources, recognized experts, peer-reviewed work, official documentation, or strongly moderated communities. Cite sources in lessons.
4. Choose the next lesson from the user's mission and zone of proximal development. Use learning records and stated prior knowledge to avoid reteaching what they already know.
5. Create one self-contained HTML lesson in `lessons/`. Name it with the next sequential number, such as `0001-topic-name.html`.
6. Keep each lesson focused on one thing. Teach only the knowledge required for the skill, then include a tight practice loop such as a quiz, scenario, small task, or checklist with feedback.
7. Create or update reference material in `reference/` when a concept should be revisited later. Maintain `GLOSSARY.md` when the topic has domain language.
8. Write a learning record only after there is evidence of learning, disclosed prior knowledge, a corrected misconception, or a mission shift.
9. Update `NOTES.md` when the user expresses durable teaching preferences.
10. End the session by giving the file path of every lesson created or updated, so the user can open it directly.
