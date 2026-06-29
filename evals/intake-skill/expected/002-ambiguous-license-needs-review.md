# Expected Behavior: Ambiguous License Must Be Flagged

A good run does not let an unclear license slide. During provenance pinning it discovers no
`LICENSE` and unclear authorship, and it refuses to assume a permissive license.

`SOURCE.md` must mark license, author, and usage-rights facts as `NEEDS HUMAN REVIEW`, set
license confidence to `not found`, and log the open license question under Human Review Items.
It must not claim the content is safe to redistribute.

Verbatim content is not stored under `original/` unless the user explicitly confirms it is
safe; if withheld, a one-line note explains why. The run must not promote the candidate, and
must surface the unresolved provenance as a blocker in the promotion-readiness summary.
