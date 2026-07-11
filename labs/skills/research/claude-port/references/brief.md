# Mode: brief

Produce today's briefing: 6–8 genuinely new items ranked for this user, each with an
interview angle. Target reading time: five minutes.

## Workflow

1. **Load state.** Read `profile.md`, the last ~60 lines of `read-log.md`, and the source
   registry (`~/.devops-research/sources.md` if present, else `references/sources.md`).
   If `digests/<today>.md` already exists, tell the user and offer a fresh sweep
   (excluding everything already delivered today) instead of silently duplicating.
   Completion: you can list the user's active prep topics, weak areas, and recently
   delivered URLs.

2. **Gather in parallel.** Build 8–12 WebSearch queries and run them in parallel batches:
   - one query per Tier 1 source group (use `site:` filters from the registry);
   - one query per active prep topic from the profile, phrased for news ("<topic> release OR announcement OR postmortem");
   - one papers query (arXiv / USENIX per the registry);
   - one incidents/security query (CVEs, outage postmortems) for the user's stack.
   Date-bound every query to the past week (past month for papers).
   Completion: ≥20 candidate items, each with url, source, and a date seen in results.

3. **Filter.** Drop, in order: read-log matches; items older than 7 days (30 for papers);
   undated items; marketing/press-release fluff with no technical content; duplicate
   coverage of one event (keep the most primary source). Use WebFetch to confirm a date
   only when the item would otherwise make the final cut.
   Completion: every survivor is dated, fresh, unread, and technical.

4. **Rank and select 6–8.** Priority order:
   1. Direct hits on active prep topics and weak areas (interviews trump curiosity).
   2. Major releases, breaking changes, CVEs, and real postmortems in the user's stack.
   3. One research paper or conference talk when a good one exists.
   4. Strong engineering-blog deep dives; think pieces last, max one.
   Completion: 6–8 items selected with at least two priority classes represented
   (or the shortfall is stated in the digest when a slow news day yields fewer).

5. **Deliver.** Format each item as:

   ```markdown
   ### 1. [Title](url) — Source, YYYY-MM-DD
   What's actually new, in 2–3 sentences with the concrete mechanism or numbers.
   **Why you care:** one sentence tied to the profile (prep topic, stack, weak area).
   **Interview angle:** the one question a senior-round interviewer would build from this.
   ```

   Open with a one-line headline of the day; close with the action line:
   `Reply: deep <n> · drill · recap`.
   Completion: every item has all four parts and a real date.

6. **Persist.** Append every delivered item to `read-log.md`, write the full briefing to
   `digests/<today>.md`, and append each interview angle to `qbank.md` (question, source
   url, date added, `last-drilled: never`).
   Completion: read-log line count grew by exactly the number of delivered items.
