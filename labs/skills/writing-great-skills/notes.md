# Notes

## What This Skill Does

A meta-skill: a reference for writing and editing other skills well. It is built around one
thesis — a skill exists to buy **predictability** (the agent taking the same *process* each
run) — and frames every technique as spending one of two budgets: **context load** (tokens
in the window from a model-invoked description) versus **cognitive load** (what the human
must remember for a user-invoked skill).

It is itself `disable-model-invocation: true` (user-invoked), all-reference / no-steps, and
it discloses its 24 term definitions to a sibling `GLOSSARY.md` via progressive disclosure.

## When It Seems Useful

- As a shared vocabulary for reviewing skill drafts (leading word, no-op, sediment, sprawl,
  duplication, completion criterion, progressive disclosure, single source of truth).
- As the craft lens our promotion pipeline was missing — see "Evaluation" below.
- As the source doctrine for an executable audit-pass run before promotion.

## When It Should Not Be Used

- As a turnkey procedure. It is a lens, not a tool: it provides vocabulary and principles
  but no ordered steps and no checkable completion criteria, so applying it as-is produces
  unpredictable results (ironic, given its own thesis). The `claude-port/` derivation fixes
  this by adding the missing audit-pass.
- As a mechanics reference. It is deep on philosophy but thin on plumbing (`name`
  conventions, `allowed-tools`, directory layout, discovery/selection). Our
  `docs/conventions.md` already covers that side.

## Evaluation (2026-06-30)

Our lab already covers two of three quality dimensions; this skill fills the third:

- Safe (provenance, secrets, hygiene) — covered by `conventions.md` / `SOURCE.md`.
- Complete (frontmatter, triggers, 2 evals, 1 worked example) — covered by
  `promotion-checklist.md`.
- Well-crafted (predictable, token-efficient, no no-ops, right invocation) — previously
  uncovered; this skill is exactly that lens.

Strengths: dogfoods its own doctrine (user-invoked, glossary disclosure, leading words);
one coherent mental model; token-dense and self-pruned; strong concrete leading-word
collapses.

Weaknesses: no steps / no completion criteria (so it is a lens, not a tool); prose density
tips into preciousness; coverage gaps on mechanics; no full worked before/after example.

Proof-point (observation only — `teach` was intentionally left untouched) — running the
doctrine on our own `teach` skill immediately found a real issue: the `## Output Expectations`
block duplicates the `## Workflow` steps (same meaning in two places) plus a couple of soft
no-ops. Recorded here as evidence the audit-pass works; no change was made to `teach`.

## Adaptation Plan

1. Done — keep upstream verbatim under `original/`.
2. Derive a Craft/Quality section in `docs/promotion-checklist.md` from the doctrine, and a
   vocabulary pointer in `docs/conventions.md`. (Lab-internal use, not a promoted skill.)
3. Draft `claude-port/SKILL.md` as the executable audit-pass: an ordered review with
   checkable completion criteria layered on the upstream reference. This is the adaptation's
   value over upstream.
4. Validate the audit-pass against `teach` as a read-only dry run (see Evaluation
   proof-point). `teach` is left unchanged.

## Test Notes

- Two eval cases exist under `evals/writing-great-skills/` (satisfies the promotion minimum):
  - `001-flags-duplication-and-no-ops` — a draft skill with an Output Expectations block
    restating its workflow plus "be thorough" / "make it look nice"; the audit must flag the
    duplication as a blocker and the no-ops, and return a verdict of fail.
  - `002-passes-clean-skill` — a lean, correctly user-invoked destructive tool with a
    checkable criterion per step; the audit must confirm it passes without inventing findings.
- Still outstanding before promotion: a worked example, and a manual run of both eval cases.
