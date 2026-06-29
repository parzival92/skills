# Conventions

## Skill Craft Vocabulary

When writing, reviewing, or discussing a skill, use the shared vocabulary defined in
`labs/skills/writing-great-skills/` (predictability, context load vs cognitive load, leading
word, completion criterion, progressive disclosure, no-op, duplication, sediment, sprawl,
single source of truth). The Craft / Quality section of `docs/promotion-checklist.md` gates
on these, and the audit-pass in that skill's `claude-port/` runs the checks.

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

Promoted skills should use this shape, one folder per supported runtime:

```text
skills/codex/skill-name/
  SKILL.md
  examples/
  scripts/
  templates/

skills/claude/skill-name/
  SKILL.md
  examples/
  scripts/
  templates/
```

A skill does not need to be promoted to every runtime at once. Promote to
`skills/codex/` and/or `skills/claude/` independently, based on which
`*-port/` candidates exist and pass the promotion checklist.

## Runtime Notes

- Codex `SKILL.md` frontmatter should stick to the minimal `name` and
  `description` fields.
- Claude Code `SKILL.md` frontmatter supports the same `name` and
  `description` fields, plus optional Claude-specific fields such as
  `allowed-tools`, `disable-model-invocation`, and `argument-hint`. Only add
  these when the skill genuinely needs them, and note their purpose in
  `notes.md`.
- When porting a skill, keep runtime-specific frontmatter out of the other
  runtime's port (e.g. strip Claude-only fields from `codex-port/SKILL.md`,
  and vice versa).

## Public Repo Hygiene

This repo is public. Before committing, check that the change contains:

- No secrets: API keys, tokens, passwords, kubeconfigs, `.env` contents, or private keys.
- No private PII: personal emails, phone numbers, addresses, employer-internal names,
  or absolute local paths like `/Users/<name>/...`.
- No paid or private source text (course material, internal docs, licensed content
  beyond what the license permits).
- No raw transcript dumps from agent sessions.

Experiment workspaces under `labs/.../experiments/` may contain personal learning
context (goals, dates, self-assessments) — that is accepted. Anything beyond that
(credentials, cluster endpoints, employer specifics) must be redacted before commit.

If something sensitive does land in a commit, treat it as leaked: rotate the secret,
then rewrite history — deleting the file in a follow-up commit is not enough.

## Evals

- Manual evals are Markdown scenarios.
- Each promoted skill needs at least two eval cases.
- Prefer realistic user requests over synthetic toy prompts.
