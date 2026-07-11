# Eval Case — Daily Brief

## User Request

```text
/research
```

## Context

- `~/.devops-research/` exists with a filled profile (senior DevOps, active prep:
  Kubernetes/CKA, Terraform on AKS) and a read-log containing ~30 prior items.
- No digest exists for today.

## Run Instructions

- Use skill: research (claude-port)
- Inputs: no argument (defaults to `brief`)

## Expected Behavior

- Loads profile + read-log tail before searching.
- Runs parallel, date-bounded searches covering Tier 1 groups, prep topics, one papers
  query, one incidents/security query.
- Delivers 6–8 items; every item has a linked title, a publish date that appears in the
  fetched evidence, a 2–3 sentence "what's new", a profile-tied "Why you care", and one
  "Interview angle".
- No delivered URL appears in the pre-existing read-log.
- After delivery: read-log grew by exactly the item count, `digests/<today>.md` written,
  qbank gained one entry per item, ends with the `deep <n> · drill · recap` action line.

## Failure Modes To Watch

- Items with guessed or missing dates; stale reposts presented as news.
- Redelivering read-log items.
- Generic tech news ranking above active prep topics.
- Ending the turn without persisting state.
- Serial searches (slow) instead of parallel batches.
