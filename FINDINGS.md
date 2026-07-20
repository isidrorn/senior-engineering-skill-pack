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

- **Java/Spring gap is a priority, not a nicety.** The strong backend skills found (e.g.
  `senior-backend`) are language-mismatched (Node). Worth a targeted hunt for a Java/Spring-tailored
  backend/architecture skill before writing one from scratch. → tracked in roadmap §4.
- **`alirezarezvani/claude-skills`** has ~40 more in-scope skills we didn't vendor (security suite,
  cloud suite, data-eng, agents). Catalogued in `research/02-skill-inventory.md`; mine as needed.
