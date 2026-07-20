# Document 1 — Ecosystem Map

Overview of the repositories surveyed while assembling the Senior Engineering Pack. Metadata
(stars, last push, license) was pulled from the **GitHub REST API and local `git`** at survey time
(**2026-07-20**), not from memory. Star counts drift daily; treat them as "order of magnitude at
survey time."

## Method & stopping point

Discovery started from the user's initial list and expanded through six community "awesome-list"
aggregators. Skills were cloned and read from **primary-source** repos; aggregator lists were read
only to harvest pointers. Discovery **stopped** once a single broad MIT repo
(`alirezarezvani/claude-skills`) was found to already cover nearly every target domain — at that
point additional repos were mostly duplicating coverage, which is the pre-agreed stopping signal.

## Primary sources (repos that host skills we read and drew from)

| Repo | Stars | Last push | License | Role in this pack |
|---|---:|---|---|---|
| [obra/superpowers](https://github.com/obra/superpowers) | 258,021 | 2026-07-20 | MIT | **Backbone of the behavior layer.** Hand-crafted, process-forcing discipline skills (root-cause debugging, TDD, verification, planning, code-review discipline). Highest-signal source for "how Claude thinks." |
| [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) | 22,894 | 2026-07-20 | Apache-2.0 | **Backbone of the engineering-workflow layer.** The official `engineering` plugin: architecture/ADR, system-design, code-review, deploy-checklist, incident-response, tech-debt, testing-strategy. Concise, authoritative, cleanly licensed. |
| [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | 22,863 | 2026-07-17 | MIT | **Domain breadth + a strong behavior spine.** 362 skills (62 in-scope) covering cloud, security, observability, data, API, AI/RAG. A vetted subset drawn for domain coverage and for standout behavior skills (zero-hallucination-coder, adversarial-reviewer). |
| [anthropics/skills](https://github.com/anthropics/skills) | 162,893 | 2026-07-17 | none at repo root; **per-skill** `LICENSE.txt` | Mostly office/creative skills (out of scope). Contributed **mcp-builder** only (its own `LICENSE.txt` is Apache-2.0). The repo-level absence of a license is a redistribution trap avoided by checking the per-skill file. |
| [ericgandrade/claude-superskills](https://github.com/ericgandrade/claude-superskills) | 60 | 2026-05-11 | MIT | Small repo; several skills are derived from superpowers. Contributed **senior-solution-architect** (C4 / ADR / DDD / Hexagonal), which fills a modeling gap the other sources lacked. |
| [isidrorn/Claude-senior-java-engineer](https://github.com/isidrorn/Claude-senior-java-engineer) | 0 | 2026-04-01 | CC-BY-4.0 | **Not a skills repo.** A Java-21 interview-prep Maven curriculum (46 modules) with three plain slash-command files and **zero `SKILL.md`**. Contributed nothing to the pack; evaluated and set aside. |

## Aggregators (index lists — read for pointers, not cloned)

All six are pure link lists that host no skills of their own. Signal-to-noise for *senior
engineering* content is generally low-to-medium; the majority of entries are Claude-Code
meta-tooling (usage monitors, hook-based observability, TDD-enforcement wrappers) rather than
transferable engineering skills.

| Aggregator | Stars | Last push | License | Senior-eng signal |
|---|---:|---|---|---|
| [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) | 68,158 | 2026-05-22 | none | Medium — some architecture / AWS / prompt-engineering pointers |
| [travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) | 14,212 | 2026-04-28 | none | Low-med — surfaced trailofbits/skills (security) |
| [BehiSecc/awesome-claude-skills](https://github.com/BehiSecc/awesome-claude-skills) | 9,809 | 2026-06-03 | none | Medium — security / AWS / debugger pointers |
| [GetBindu/awesome-claude-code-and-skills](https://github.com/GetBindu/awesome-claude-code-and-skills) | 169 | 2026-07-11 | Apache-2.0 | Medium — best RAG / knowledge-graph / arch-doc coverage |
| [subinium/awesome-claude-code](https://github.com/subinium/awesome-claude-code) | 100 | 2026-04-25 | none | Med-high — best cloud-native / K8s / MCP-ecosystem concentration |
| [itgoyo/awesome-claude-code-skills](https://github.com/itgoyo/awesome-claude-code-skills) | 37 | 2026-04-13 | none | Low — thinnest list |

## Notable repos surfaced but not drawn from (candidates for the next iteration)

These are real skill sources that would mostly **duplicate** what `alirezarezvani/claude-skills`
already provides, so they were not pursued for v0.1. Several are higher-credibility than the generic
aggregated skills and are worth evaluating when the pack is refined (see
`05-personalization-roadmap.md`):

- **[trailofbits/skills](https://github.com/trailofbits/skills)** — professional static-analysis /
  security-audit tooling (CodeQL/Semgrep) from a top security firm. Likely higher quality than the
  aggregated security skills.
- **[zxkane/aws-skills](https://github.com/zxkane/aws-skills)** — AWS CDK, cost optimization,
  serverless / event-driven patterns (appeared in two lists).
- **NeoLabHQ/software-architecture** — Clean Architecture / SOLID / design patterns.
- **agamm/claude-code-owasp** — OWASP Top-10 / ASVS security-review checklists.
- **supabase/agent-skills** — Postgres / RLS / query-tuning backend practices.
- **hashicorp/agent-skills** — HashiCorp-maintained Terraform workflow skills.

## Explicitly excluded as "not skills"

Many aggregator "candidates" are **MCP servers or tools**, not reasoning skills, and do not belong
in a *skills* pack: `containers/kubernetes-mcp-server`, `hashicorp/terraform-mcp-server`,
`grafana/mcp-grafana`, `kubernetes-sigs/agent-sandbox`, `modelcontextprotocol/*`, and
observability/token-monitoring meta-tooling (`tdd-guard`, `agenttrace`, `agnix`). They are noted in
the roadmap as complementary infrastructure the pack could *pair with*, not absorb.
