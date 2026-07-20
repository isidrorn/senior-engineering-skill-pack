# Findings — useful, but out of current scope

A running register of things worth remembering that **don't belong in the skills pack itself** but
could help the user's engineering workflow. Flagged here so good discoveries don't evaporate. Add to
this whenever something useful-but-off-scope turns up.

## Complementary MCP servers (pair with the pack's reasoning skills, live in your MCP config)

These are **tools/servers, not skills** — but they're the hands for several skills' brains:

| MCP server | Pairs well with | What it does |
|---|---|---|
| [containers/kubernetes-mcp-server](https://github.com/containers/kubernetes-mcp-server) | ship-gate, incident-response, chaos-engineering | K8s/OpenShift CRUD, Helm, multi-cluster ops (Go) |
| [hashicorp/terraform-mcp-server](https://github.com/hashicorp/terraform-mcp-server) | tech-stack-evaluator, deploy-checklist | Terraform Registry / IaC automation |
| [grafana/mcp-grafana](https://github.com/grafana/mcp-grafana) | observability-designer, slo-architect, incident-response | Query Prometheus/Loki, manage alerts/dashboards |
| [modelcontextprotocol/inspector](https://github.com/modelcontextprotocol/inspector) | mcp-builder | Visual MCP debugging |
| [zilliztech/claude-context](https://github.com/zilliztech/claude-context) | rag-architect, codebase work | Semantic (vector) codebase search |

## Skill repos to evaluate in a later pass (would extend coverage; not needed for v0.1)

- [trailofbits/skills](https://github.com/trailofbits/skills) — CodeQL/Semgrep security audit, high credibility → **Security lane**
- [agamm/claude-code-owasp](https://github.com/agamm/claude-code-owasp) — OWASP Top-10 / ASVS review → **Security lane**
- [zxkane/aws-skills](https://github.com/zxkane/aws-skills) — AWS CDK, cost, serverless/EDA → **Cloud-native design**
- [hashicorp/agent-skills](https://github.com/hashicorp/agent-skills) — Terraform workflow → **Cloud-native / IaC**
- NeoLabHQ/software-architecture — Clean Arch / SOLID / patterns
- supabase/agent-skills — Postgres / RLS / query tuning → **backend/data**
- mturac/recsys-pipeline-architect — pipeline architecture + trade-off analysis

## Workflow / meta tooling (for the user's own setup, not the pack)

- **agent-config linters/observability** — `avifenesh/agnix` (lint SKILL.md/CLAUDE.md/hooks),
  `luoyuctl/agenttrace` (local session cost/latency TUI), `disler/…-multi-agent-observability`.
  Potentially handy while *building* this pack; not skills to ship.

## Open threads flagged during the project

- ✅ **Java/Spring gap — RESOLVED (round 2).** A targeted hunt found strong Java/Spring skills:
  vendored 22 (Boot 4) from `rrezartprebreza/spring-boot-skills` + `piomin/claude-ai-spring-boot`
  (Piotr Mińkowski) + `Jeffallan/claude-skills` (java-architect). Lesson: language-specific hunting
  matters — the round-1 "gap" was an artifact of not searching for Java-tailored skills.
- ✅ **Distributed systems / event-driven — RESOLVED (round 2)** via `sethdford/claude-skills` (10
  skills). These repos are now *used*, not just flagged.
- **Still open:** dedicated **Security** lane (trailofbits/OWASP) and **Cloud-native/K8s design** —
  see roadmap §3.
- **`alirezarezvani/claude-skills`** has ~40 more in-scope skills we didn't vendor (security suite,
  cloud suite, data-eng, agents). Catalogued in `research/02-skill-inventory.md`; mine as needed.
- **`sethdford/claude-skills`** has ~245 more skills beyond the 10 taken (large architect/design/data
  toolkit) — a rich seam for future architecture/data-modeling additions.
