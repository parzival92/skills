---
name: research
description: Daily DevOps/SRE research briefing, deep dives, and interview drills built from fresh articles, releases, and papers. Use when the user asks for their daily brief, "what's new" in DevOps/Kubernetes/platform engineering/cloud, a deep dive on an article/paper/topic, an interview drill from recent reads, or a weekly recap.
argument-hint: "[brief | deep <n|url|topic> | drill [topic] | recap]"
---

# Research — Daily DevOps Briefing & Interview Prep

A stateful research loop for a senior DevOps engineer: gather what is genuinely new,
never repeat an item, and convert every read into interview ammunition.

Do not use this skill for one-off factual lookups or debugging questions — answer
those directly.

## State

All state lives in `~/Developer/devops-research/`:

- `profile.md` — who the user is, active prep topics, weak areas. Loaded by every mode.
- `read-log.md` — one line per delivered item: `YYYY-MM-DD | title | url`. The dedupe source of truth.
- `qbank.md` — interview question bank grown from reads. Each entry: question, source url, date added, `last-drilled:` date and result.
- `digests/YYYY-MM-DD.md` — the delivered daily briefs.
- `sources.md` — optional user override; when present it replaces `references/sources.md`.

If `~/Developer/devops-research/profile.md` does not exist, run first-time setup before the
requested mode: create the directory, copy `templates/profile.md` into it, fill it from
what the conversation and memory already establish about the user, show the user the
profile, and ask them to correct it. Setup is complete when the profile is confirmed.

## Modes

Route on the argument; no argument means `brief`. Read only the file for the chosen mode:

| Mode | When | Workflow |
|---|---|---|
| `brief` | Daily read; "what's new" | `references/brief.md` |
| `deep <n\|url\|topic>` | Full teardown of one item (`n` = item number from today's digest) | `references/deep-dive.md` |
| `drill [topic]` | Interview quiz from recent reads + weak areas | `references/drill.md` |
| `recap` | Weekly synthesis + spaced recall | `references/recap.md` |

## Rules that bind every mode

- **Freshness is evidence-gated.** Every delivered item carries a publish date you have
  actually seen (in search results or on the page). An item with no verifiable date, or a
  repost of old news, is discarded — never delivered with a guessed date.
- **Never redeliver.** Check candidate URLs and titles against `read-log.md` before
  delivery; a match is silently dropped.
- **Persist before ending the turn.** A mode is not finished until its writes (read-log,
  digest, qbank, profile updates) are on disk — the next session depends on them. When
  `~/Developer/devops-research` is a git repo, also commit the writes with message
  `<mode>: YYYY-MM-DD` and push if a remote exists.
- **Interview lens always on.** Content is selected and summarized for what a senior
  DevOps/platform interview loop would probe, not for general readership.
