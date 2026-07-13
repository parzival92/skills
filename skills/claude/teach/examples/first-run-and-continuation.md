# Worked Example: First Run and Continuation

A condensed two-session walkthrough of the skill's core loop. Topic and user are
fictional; the shape mirrors real dogfooding sessions (kept outside this repo).

## Session 1 — first run in an empty directory

**User:** "Teach me SQL window functions."

The workspace has no `MISSION.md`, so the skill interviews before teaching:

> Before I build anything: what do you need window functions *for*? What would
> success look like in your actual work? Any constraints — time, database
> engine, things you already know? Anything explicitly out of scope?

**User:** "I'm a support engineer moving into analytics. I need to answer
'top-N per group' and running-total questions on Postgres for weekly reports.
I know basic SELECT/GROUP BY. Maybe 30 minutes a day. Skip query tuning."

The skill then writes the workspace, in this order:

1. `MISSION.md` (per `MISSION-FORMAT.md`) — why: weekly analytics reports;
   success: writes top-N-per-group and running-total queries unaided on
   Postgres; constraints: 30 min/day, Postgres 16; out of scope: tuning.
2. `RESOURCES.md` (per `RESOURCES-FORMAT.md`) — official PostgreSQL docs
   (window functions chapter), annotated; a gap noted for practice datasets.
3. `lessons/0001-rank-vs-row-number.html` — one tightly scoped lesson:
   `ROW_NUMBER` vs `RANK` vs `DENSE_RANK`, citing the Postgres docs, ending in
   a practice loop (three "top-N per group" exercises against a sample table).

No learning record is written — nothing has been demonstrated yet. The session
ends with the lesson's file path.

## Session 2 — continuation

**User:** "What should I learn next?"

The skill inspects the workspace first: mission, resources, `lessons/`,
`learning-records/`, `NOTES.md`. The user then pastes their solutions to
lesson 0001's exercises; two are correct, one confuses `RANK` gaps with
`DENSE_RANK`. The skill:

1. Corrects the misconception with a minimal counter-example.
2. Writes `learning-records/0001-ranking-functions-demonstrated.md` (per
   `LEARNING-RECORD-FORMAT.md`) — understanding demonstrated for ranking
   functions; misconception about `RANK` gaps corrected.
3. Adds `GLOSSARY.md` entries (per `GLOSSARY-FORMAT.md`) for **window frame**
   and **partition** — terms the user now uses correctly.
4. Chooses the next lesson inside the zone of proximal development —
   `lessons/0002-running-totals-with-frames.html` — building on partitions,
   not reteaching ranking.

## What this example is meant to show

- Mission interview happens **before** any teaching (session 1).
- Learning records appear only after **evidence**, never after mere delivery
  (session 1 writes none; session 2 writes one).
- Each lesson teaches one thing and ends in a practice loop.
- Continuation sessions read state first and never reteach demonstrated
  knowledge.
