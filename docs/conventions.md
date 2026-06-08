# Conventions

## Naming

- Use lowercase kebab-case for skill folder names.
- Keep external experiments under `labs/skills/<skill-name>/`.
- Keep promoted Codex skills under `skills/codex/<skill-name>/`.

## Provenance

- Every copied external skill needs `SOURCE.md`.
- Use `NEEDS HUMAN REVIEW` for uncertain author, license, or source facts.
- Do not claim a license is safe unless the source explicitly says so.
- Store exact originals only when license and size allow.

## Skill Packages

Promoted Codex skills should use this shape:

```text
skills/codex/skill-name/
  SKILL.md
  examples/
  scripts/
  templates/
```

## Evals

- Manual evals are Markdown scenarios.
- Each promoted skill needs at least two eval cases.
- Prefer realistic user requests over synthetic toy prompts.
