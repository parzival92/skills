---
name: intake-skill
description: Ingest an external skill into this lab with pinned provenance. Use when the user wants to intake, ingest, adapt, vendor, or copy an external skill, prompt, or repo into labs/skills/, or says "bring in this skill".
---

# Intake Skill

Use this skill to bring an external skill (or prompt/repo) into `labs/skills/<skill-name>/`
with honest, pinned provenance and a draft port — the first half of the
`Idea → Intake → Lab → Port → Eval → Promotion` pipeline.

Do not use this skill to promote a candidate into `skills/codex/` or `skills/claude/` (that is
`promote-skill` / `docs/promotion-checklist.md`), and do not use it to author an original
skill from scratch (there is no external source to track).

Follow the lab rules in `AGENTS.md`, `docs/conventions.md`, and the public-repo hygiene rules
in `docs/conventions.md`. Mark any uncertain author, license, or source fact as
`NEEDS HUMAN REVIEW` — never guess provenance.

## Workflow

1. **Fix the source and the skill name.** Get the source URL or path, and choose a
   lowercase kebab-case `<skill-name>`. Done when both are known and no existing
   `labs/skills/<skill-name>/` would be overwritten without the user's go-ahead.

2. **Pin provenance before copying anything.** Identify the license and copyright holder
   from the source repo's `LICENSE`, the latest commit SHA touching the source path, and the
   exact list of files the source contains. Done when you hold a confirmed license (or
   `NEEDS HUMAN REVIEW`), a commit SHA to pin, and an enumerated file list — none assumed.

3. **Store verbatim originals.** Copy every upstream file plus its `LICENSE` into
   `labs/skills/<skill-name>/original/`, but only when the license and size allow. Done when
   `original/` byte-for-byte matches the pinned source, or a one-line note records why a file
   was omitted.

4. **Write `SOURCE.md`.** Fill `templates/lab-skill/SOURCE.md`: skill name, source type,
   author, source URL, pinned commit SHA, pinned source URL, date, license, and license
   confidence. Done when no required field is blank and every uncertain fact reads
   `NEEDS HUMAN REVIEW`.

5. **Write `notes.md`.** Fill `templates/lab-skill/notes.md`: what the skill does, when it is
   useful, when it must not be used, and the adaptation plan. Done when all four sections are
   filled in plain language, not restated frontmatter.

6. **Draft the runtime port(s).** Create `claude-port/SKILL.md` and/or `codex-port/SKILL.md`
   from the original, stripping each runtime's metadata from the other (Claude-only fields out
   of the Codex port, and vice versa — see `docs/conventions.md`). Done when at least one port
   exists and its frontmatter obeys the runtime's rules.

7. **Scaffold evaluations.** Create at least two realistic cases under
   `evals/<skill-name>/cases/` from `templates/eval-case.md`, each with a matching file under
   `evals/<skill-name>/expected/`. Done when two case/expected pairs exist and describe real
   user requests, not toy prompts.

8. **Report, do not promote.** Summarise what landed and list what still blocks promotion
   against `docs/promotion-checklist.md` (worked example, manual eval run, unresolved
   `NEEDS HUMAN REVIEW` items). Done when the user has a clear promotion-readiness list and
   nothing was written under `skills/codex/` or `skills/claude/`.
