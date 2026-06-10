# Skills Lab

A structured repository for experimenting with, adapting, evaluating, and packaging reusable `SKILL.md` workflows for Codex and Claude Code.

The project keeps rough experiments separate from promoted skills. External material is tracked with provenance notes, runtime-specific adaptations are maintained independently, and candidate skills are checked against realistic evaluation cases before promotion.

## Purpose

- Explore skill ideas without treating early experiments as finished packages.
- Preserve source, author, license, and adaptation context for external skills.
- Maintain separate Codex and Claude Code ports when runtime behavior differs.
- Test skills with realistic manual evaluation cases and expected outcomes.
- Promote only the skills that are documented, reproducible, and safe to reuse.

## Workflow

```text
Idea -> Intake -> Lab Experiment -> Runtime Port -> Evaluation -> Promotion
```

1. Record rough ideas in [`labs/inbox.md`](labs/inbox.md).
2. Create a lab workspace under `labs/skills/<skill-name>/`.
3. Document provenance and licensing context in `SOURCE.md`.
4. Keep copied source separate from adaptations and experiments.
5. Draft Codex and/or Claude Code candidates in their runtime-specific port folders.
6. Add at least two realistic evaluation cases with expected behavior.
7. Run the [promotion checklist](docs/promotion-checklist.md) before moving a skill into a published runtime package.

## Repository Structure

```text
labs/
  inbox.md
  skills/
    skill-name/
      SOURCE.md
      notes.md
      original/
      experiments/
      codex-port/
      claude-port/

skills/
  codex/
    skill-name/
      SKILL.md
      examples/
      scripts/
      templates/
  claude/
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
  claude-skill/
  eval-case.md

prompts/
  intake-external-skill.md

docs/
  conventions.md
  promotion-checklist.md
```

## Quality Gates

A skill is ready for promotion only when:

- Provenance and usage rights are documented without unresolved critical gaps.
- `SKILL.md` follows the target runtime format.
- Trigger guidance and "do not use" guidance are clear.
- At least two realistic evaluation cases and expected outcomes exist.
- At least one worked example is included.
- Referenced scripts and templates exist.
- The package does not depend on hidden secrets or one-off local context.

See [`docs/promotion-checklist.md`](docs/promotion-checklist.md) for the complete checklist.

## Key Documents

| Document | Purpose |
| --- | --- |
| [`docs/conventions.md`](docs/conventions.md) | Naming, provenance, runtime packaging, public repository hygiene, and evaluation rules |
| [`docs/promotion-checklist.md`](docs/promotion-checklist.md) | Required checks before a skill is promoted |
| [`prompts/intake-external-skill.md`](prompts/intake-external-skill.md) | Repeatable intake prompt for adapting an external skill |
| [`labs/inbox.md`](labs/inbox.md) | Staging area for skill ideas before creating a full lab workspace |

## Runtime Model

Codex and Claude Code use `SKILL.md` as the executable skill format, but runtime-specific metadata and behavior may differ. This repository keeps their ports and promoted packages separate so each runtime can evolve without leaking incompatible configuration into the other.

A skill can be promoted for one runtime before the other when only one port has passed its evaluation and promotion checks.

## Public Repository Safety

Before committing, check that changes contain no credentials, kubeconfigs, private environment values, employer-internal information, private personal data, paid source material, or raw agent transcripts. If sensitive data reaches Git history, rotate the secret and rewrite the affected history.
