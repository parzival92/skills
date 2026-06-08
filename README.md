# Skills Lab

This repo is a hybrid lab and library for experimenting with LLM skills, adapting useful external skills, testing them on real ideas, and promoting the useful ones into polished Codex-compatible packages.

The repo is Codex-first today, but the structure is intentionally runtime-agnostic. Codex `SKILL.md` packages are the canonical executable format for now; other LLM or agent formats can be added later as explicit ports or adapters.

## Layout

```text
labs/
  inbox.md
  skills/
    skill-name/
      SOURCE.md
      original/
      experiments/
      codex-port/

skills/
  codex/
    skill-name/
      SKILL.md
      examples/
      scripts/
      templates/

evals/
  skill-name/
    cases/
    expected/
    notes.md

templates/
  lab-skill/
  codex-skill/
  eval-case.md

prompts/
  intake-external-skill.md

docs/
  conventions.md
  promotion-checklist.md
```

## Normal Workflow

1. Copy or link an external skill into `labs/skills/<skill-name>/`.
2. Fill `SOURCE.md` with provenance, license, and uncertainty notes.
3. Keep exact copied source in `original/` when license and size allow.
4. Try messy changes in `experiments/`.
5. Draft a Codex candidate in `codex-port/`.
6. Add at least two manual eval cases under `evals/<skill-name>/`.
7. Promote mature work into `skills/codex/<skill-name>/`.

Use `prompts/intake-external-skill.md` when asking Codex to fill the intake files for a copied skill.
