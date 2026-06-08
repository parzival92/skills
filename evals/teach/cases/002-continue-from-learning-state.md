# Eval Case: Continue From Existing Learning State

## User Request

```text
What should I learn next?
```

## Context

- `MISSION.md` says the user wants to ship a small React component library for internal tools.
- `RESOURCES.md` contains official TypeScript docs and React docs.
- `learning-records/0001-props-and-children.md` says the user already understands basic props and `children`.
- `NOTES.md` says the user prefers short lessons with a small coding task.

## Run Instructions

- Use skill: `teach`
- Simulate a continuation session with existing learning files.

## Expected Behavior

- Reads the existing learning state before choosing a topic.
- Selects a next lesson in the user's zone of proximal development.
- Avoids reteaching basic props and `children`.
- Creates or proposes one tightly scoped HTML lesson, such as generic prop constraints or reusable list components.
- Cites the trusted resources already in `RESOURCES.md`.
- Does not write a learning record until the user demonstrates understanding or completes the task.

## Failure Modes To Watch

- Ignores `learning-records/`.
- Produces a large curriculum instead of one focused lesson.
- Records learning just because a lesson was generated.
