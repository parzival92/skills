# Source Registry (default)

Query building blocks for `brief` step 2. Copy this file to
`~/.devops-research/sources.md` and edit it there to customize — the state-dir copy wins.

## Tier 1 — sweep every brief (one query per group)

| Group | `site:` filter / query core |
|---|---|
| Kubernetes & CNCF | `site:kubernetes.io/blog OR site:cncf.io/blog` |
| Cloud providers | `site:aws.amazon.com/blogs OR site:azure.microsoft.com/en-us/blog OR site:cloud.google.com/blog` |
| IaC & delivery | `site:hashicorp.com/blog OR site:github.blog OR site:about.gitlab.com/blog OR site:argoproj.github.io` |
| Observability | `site:grafana.com/blog OR site:prometheus.io/blog OR site:opentelemetry.io/blog` |
| Aggregators | `site:news.ycombinator.com` + topic keywords (kubernetes, terraform, sre, platform engineering) |

## Tier 2 — rotate 2–3 per brief

- InfoQ DevOps (`site:infoq.com/devops`), The New Stack (`site:thenewstack.io`)
- Big-tech engineering blogs: `site:netflixtechblog.com OR site:eng.uber.com OR site:engineering.fb.com OR site:blog.cloudflare.com OR site:slack.engineering OR site:shopify.engineering`
- Newsletters as indexes: SRE Weekly (`site:sreweekly.com`), DevOps'ish, Last Week in AWS
- LWN (`site:lwn.net`) for kernel/container runtime depth

## Papers & talks (one query per brief, past month)

- arXiv: `site:arxiv.org (cs.DC OR cs.SE OR cs.OS)` + topic keywords
- USENIX: `site:usenix.org` — SREcon, NSDI, OSDI, ATC, LISA proceedings and talks

## Incidents & security (one query per brief)

- CVEs and advisories for the user's stack: `kubernetes OR containerd OR terraform OR nginx CVE advisory`
- Postmortems: `postmortem OR "incident report" OR outage` + stack keywords; `site:status.cloud.google.com OR site:health.aws.amazon.com` for major cloud incidents

## Query rules

- Always add a freshness bound: "past week" phrasing plus the current month/year in the
  query, or the search tool's date filter when available.
- Prefer primary sources; when an aggregator hit points at an original post, deliver the
  original URL.
