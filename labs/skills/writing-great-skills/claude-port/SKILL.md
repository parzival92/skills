---
name: writing-great-skills
description: Audit a SKILL.md for craft — predictability, invocation fit, duplication, no-ops, completion criteria, leading words, and disclosure — and emit fixes.
disable-model-invocation: true
argument-hint: "Path to the SKILL.md to audit"
---

# Writing Great Skills — Audit Pass

Use this skill to review a skill draft for craft before promotion: invocation fit,
duplication, no-ops, completion criteria, leading words, and progressive disclosure.

Do not use this skill to check completeness or safety (provenance, evals, worked example,
secrets) — that is `docs/promotion-checklist.md` Required. This is the Craft / Quality gate.

The doctrine and full definitions behind every check live in `../original/SKILL.md` and
`../original/GLOSSARY.md`. Read a term there when a finding needs justifying; otherwise the
checks below are self-contained. The root virtue is **predictability**: the agent taking the
same *process* every run.

## Workflow

Run the steps in order on the target `SKILL.md`. Produce one finding per issue as you go;
each finding records `severity` (blocker / craft / nit), the location, the problem, and a
concrete fix. Do not stop at the first issue in a step — a step is done only when the whole
file has been swept for that step's concern.

1. **Read the whole skill and its linked files.** Read the target `SKILL.md` and every file
   it points at (glossaries, format files, scripts). Completion: you can name every file the
   skill loads and every distinct **branch** (way the skill is used). No finding yet.

2. **Audit invocation fit.** Decide whether the frontmatter matches how the skill is
   actually reached. `disable-model-invocation: true` belongs on a skill that only ever fires
   by hand; a model-invoked description belongs only when the agent or another skill must
   reach it autonomously. Completion: the invocation choice is either confirmed justified or
   a finding proposes the switch (and, if model-invoked, the description front-loads the
   leading word and carries one trigger per branch — no synonym restatements).

3. **Hunt duplication (single source of truth).** Find any meaning stated in more than one
   place. Watch specifically for an "Output Expectations" / summary block that restates the
   workflow steps. Completion: every duplicated meaning has a finding that names both
   locations and picks the one authoritative home (usually a per-step completion criterion),
   or the sweep found none.

4. **Hunt no-ops sentence by sentence.** Test each sentence in isolation: does it change
   behaviour versus the model's default? Flag weak instructions ("be thorough", "keep it
   nice", "make it easy") that the agent already obeys. Completion: every sentence has been
   tested; each failing one has a finding that either deletes the whole sentence or replaces
   it with a stronger **leading word**.

5. **Audit completion criteria.** For each step, check it ends on a condition the agent can
   tell done-from-not-done, and that it is exhaustive where it matters ("every modified file
   accounted for", not "produce a list"). Completion: every step either has a checkable
   criterion or has a finding that rewrites the fuzzy one (guards against **premature
   completion**).

6. **Hunt leading-word refactors.** Find restated triads or fuzzy phrases that collapse into
   one pretrained concept (e.g. "fast, deterministic, low-overhead" → *tight*). Completion:
   each candidate either has a finding proposing the word, or you have confirmed no stronger
   word exists.

7. **Audit disclosure and sprawl.** Check that reference only some branches need sits behind
   a context pointer, that inlined material is what every branch needs, and that the file
   is not bloated with stale layers (**sediment**) or simply too long (**sprawl**).
   Completion: each over-inlined block has a finding proposing a move down the hierarchy, or
   the structure is confirmed sound.

8. **Emit the findings report.** Group findings by severity (blockers first). For each: the
   location, the problem in one line, and the concrete fix. End with a one-line verdict:
   does the skill pass the Craft / Quality gate, and if not, the smallest set of blockers
   that would make it pass. Completion: the report covers every finding from steps 2–7 and
   maps cleanly onto the Craft / Quality bullets in `docs/promotion-checklist.md`.

## Output Expectations

(intentionally none — every expectation is a completion criterion on the step that produces
it, to keep a single source of truth.)
