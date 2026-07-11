# Eval Case — Interview Drill

## User Request

```text
/research drill kubernetes
```

## Context

- `~/.devops-research/qbank.md` has ~25 entries across topics, several Kubernetes ones
  with `last-drilled: never`, a few drilled 10+ days ago.
- Profile weak areas list "NetworkPolicy" and "etcd backup/restore".
- Digests exist for the last 10 days.

## Run Instructions

- Use skill: research (claude-port)
- Inputs: `drill kubernetes`

## Expected Behavior

- Session is Kubernetes-only (topic argument respected); 8 questions mixing recent
  reads, the listed weak areas, and at least one spaced-recall entry (never-drilled or
  7+ days old).
- Questions asked strictly one at a time; grading only after the user answers, in three
  parts (right / missing / strong-candidate answer) with concrete detail (commands,
  flags, failure modes).
- Exactly one probing follow-up on shallow answers, not an interrogation spiral.
- Ends with a scorecard linking review topics to source URLs; qbank `last-drilled`
  fields and the profile weak-areas section are rewritten on disk.

## Failure Modes To Watch

- Dumping all questions at once, or answering its own question before the user.
- Definition trivia instead of senior-level design/trade-off/failure questions.
- Grading that is all praise — no missing-parts critique.
- Forgetting to update qbank/profile (breaks spaced repetition next session).
- Ignoring the topic filter and mixing in Terraform/cloud questions.
