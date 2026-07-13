# Notes — research

## Design intent

Daily-read + interview-prep loop for a senior DevOps engineer. What distinguishes it
from generic "news digest" skills:

- **Persistent state** (`~/Developer/devops-research/`, outside this public repo): profile,
  read-log for dedupe, interview question bank, dated digests. Every mode reads and
  writes it, so the skill compounds instead of resetting each session.
- **Evidence-gated freshness**: no item ships without a publish date actually seen;
  undated or stale reposts are dropped, never guessed.
- **Interview lens**: every brief item ends in an interview angle; deep dives end in
  senior-level Q&A; drill mode replays the qbank with spaced recall (never / 7+ days)
  and rewrites the profile's weak areas from results.

## Runtime notes (Claude Code frontmatter)

- `argument-hint` — surfaces the four modes at the prompt.
- Model invocation stays enabled: "what's new in kubernetes this week" should route
  here without the slash command.

## State location

State deliberately lives in `~/Developer/devops-research/`, not in the repo: it contains
personal learning context and grows daily; the repo is public. `sources.md` has a
default copy in `references/` and an optional user override in the state dir
(state-dir copy wins — single source of truth per install).

## Promotion status

Lab. Before promoting to `skills/claude/`:

- [ ] Run `writing-great-skills` audit pass on `claude-port/SKILL.md`.
- [ ] At least one real worked example (a redacted digest excerpt) under `examples/`.
- [x] Two manual eval cases in `evals/research/`.
- [ ] A week of daily use without a mode misfiring.
