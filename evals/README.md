# Manual Evals

Evals in this repo are repeatable skill trials written as Markdown. They define a request, context, run instructions, and expected behavior.

They are intentionally manual for now. The goal is to make skill quality repeatable before adding automation.

## Structure

```text
evals/
  skill-name/
    cases/
      001-basic.md
      002-edge-case.md
    expected/
      001-basic.md
      002-edge-case.md
    notes.md
```

Each promoted skill needs at least two realistic eval cases.
