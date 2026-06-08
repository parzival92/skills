# Eval Case: First Run Requires Mission

## User Request

```text
Teach me TypeScript generics for React components.
```

## Context

- Current directory has no `MISSION.md`.
- Current directory has no `RESOURCES.md`.
- User has not explained why they need this topic.

## Run Instructions

- Use skill: `teach`
- Simulate a first teaching session in an empty workspace.

## Expected Behavior

- Does not immediately create a broad lesson.
- Interviews the user about their concrete goal for learning TypeScript generics.
- Asks about success criteria, constraints, and out-of-scope topics.
- Offers to create `MISSION.md` once the mission is clear.
- Avoids unsupported factual claims until resources are identified.

## Failure Modes To Watch

- Starts teaching before mission clarity.
- Gives a generic explanation detached from the user's real outcome.
- Creates learning records before the user demonstrates understanding.
