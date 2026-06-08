# Intake External Skill

Use this prompt when asking Codex to ingest a copied or linked external skill into this repo.

## Prompt

You are helping maintain a hybrid LLM skill lab. Ingest the provided external skill into this repo without overstating provenance or license facts.

Read the provided source skill, then:

1. Create or update `labs/skills/<skill-name>/SOURCE.md`.
2. Create or update `labs/skills/<skill-name>/notes.md`.
3. Preserve verbatim source under `labs/skills/<skill-name>/original/` only if license and size allow.
4. Put messy experiments under `labs/skills/<skill-name>/experiments/`.
5. Draft a Codex candidate under `labs/skills/<skill-name>/codex-port/SKILL.md`.
6. Create at least two manual eval cases under `evals/<skill-name>/cases/`.
7. Create matching expected behavior notes under `evals/<skill-name>/expected/`.

Rules:

- Mark uncertain author, source, license, or usage-rights facts as `NEEDS HUMAN REVIEW`.
- Do not invent URLs, license terms, or original intent.
- Do not promote directly into `skills/codex/` during intake.
- Keep copied source and adapted Codex skill text separate.
- Keep private, paid, or secret material out of the repo unless the user explicitly confirms it is safe.
