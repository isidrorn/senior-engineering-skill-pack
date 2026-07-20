# Document 2 — Skill Inventory

Catalog of every **relevant** skill found across the primary sources. "Relevant" = passes the
intake filter (behavior-changing engineering reasoning **or** a target domain). Out-of-scope skills
(office/creative/business/vendor-SDK) are counted in aggregate only.

**Schema:** `skill · purpose · category · behavior|knowledge · domain-fit · cluster`. Per-skill
`last_update`, `popularity`, and `license` are inherited from the source repo (see
[Document 1](01-ecosystem-map.md)) unless a skill ships its own — noted where so. `cluster` IDs feed
the dedup analysis in [Document 3](03-skill-evaluation.md).

## Relevant-skill counts per source

| Source | Total skills | Relevant | Notes |
|---|---:|---:|---|
| obra/superpowers | 14 | 10 | Behavior discipline; 4 out-of-scope are Claude-workflow meta (worktrees, writing-skills) |
| anthropics/knowledge-work-plugins | 212 | 9 | All in the `engineering` plugin; other 200+ are business/vendor-SDK |
| alirezarezvani/claude-skills | 362 | 62 | 300 out-of-scope: c-level (68), marketing (49), regulatory/QMS (19), product (17), etc. |
| anthropics/skills | 18 | 2 (+1 borderline) | 15 out-of-scope office/creative |
| ericgandrade/claude-superskills | 18 | 5 | 13 out-of-scope (research/storytelling/office) |

---

## obra/superpowers (MIT · 258k★ · behavior discipline, hand-crafted)

| skill | purpose | category | b/k | domain | cluster |
|---|---|---|---|---|---|
| systematic-debugging | Root-cause-first "Iron Law" before any fix; 4 phases | Debugging | behavior | RCA | C2 |
| test-driven-development | Tests before implementation, red-green-refactor | Testing | behavior | TDD | C6 |
| verification-before-completion | Require running verification + evidence before "done" | Production | behavior | prod-readiness | C7 |
| writing-plans | Turn spec into a written plan before coding | Workflow | behavior | design-before-code | C1 |
| brainstorming | Force ideation/requirements before building | Workflow | behavior | design-before-code | C1 |
| requesting-code-review | Verify work meets requirements before requesting review | Review | behavior | code-review | C3 |
| receiving-code-review | Rigorous, non-performative handling of review feedback | Review | behavior | code-review | C3 |
| executing-plans | Execute a written plan in a separate session w/ checkpoints | Workflow | behavior | planning | C1 |
| subagent-driven-development | Execute plans via independent subagent tasks | Workflow | behavior | planning | — |
| finishing-a-development-branch | Merge/PR/cleanup decision guide once tests pass | CI/CD | behavior | workflow | — |

## anthropics/knowledge-work-plugins → engineering plugin (Apache-2.0 · 22.9k★ · official)

| skill | purpose | category | b/k | domain | cluster |
|---|---|---|---|---|---|
| architecture | Create/evaluate ADRs; choose between technologies | Architecture | behavior | architecture | C4 |
| system-design | Design services/APIs; data modeling; service boundaries | System Design | behavior | system design, distributed | C5 |
| code-review | Review diffs for security/perf/correctness (N+1, injection) | Review | behavior | security, perf | C3 |
| debug | Reproduce/isolate/diagnose/fix; prod-vs-staging divergence | Debugging | behavior | production | C2 |
| deploy-checklist | Pre-deploy checklist: migrations, flags, CI, rollback triggers | Production | behavior | CI/CD, production | C7 |
| incident-response | Triage, communicate, blameless postmortem | Incident | behavior | production, observability | C8 |
| tech-debt | Identify/categorize/prioritize refactoring backlog | Tech Debt | behavior | maintenance | C12 |
| testing-strategy | Design test strategy, plan, coverage approach | Testing | behavior | testing | C6 |
| documentation | API docs, architecture docs, runbooks | Documentation | knowledge | architecture, API | C18 |

## anthropics/skills (per-skill license · 163k★)

| skill | purpose | category | b/k | domain | cluster | license |
|---|---|---|---|---|---|---|
| mcp-builder | Build production MCP servers (FastMCP / TS SDK) from API contracts | AI Eng | behavior | AI eng, LLM, API | C15 | Apache-2.0 (own LICENSE.txt) |
| claude-api | Claude API reference: models, pricing, streaming, caching | AI Eng | knowledge | AI eng, LLM | C15 | per-skill |
| webapp-testing | Playwright toolkit for local web-app functional verification | Testing | behavior | testing | C6 | per-skill |

## ericgandrade/claude-superskills (MIT · 60★)

| skill | purpose | category | b/k | domain | cluster |
|---|---|---|---|---|---|
| senior-solution-architect | C4 diagrams, ADRs (MADR/Y-Statement), Clean/Hexagonal/DDD | Architecture | behavior | architecture, DDD | C4 |
| prompt-engineer | Create/improve/optimize prompts | AI Eng | behavior | LLM | C15 |
| brainstorming | Pre-implementation ideation (derived from superpowers) | Workflow | behavior | design-before-code | C1 |
| writing-plans | Spec→plan before code (derived from superpowers) | Workflow | behavior | planning | C1 |
| executing-plans | Execute plan in separate session (derived from superpowers) | Workflow | behavior | planning | C1 |

## alirezarezvani/claude-skills — 62 relevant (MIT · 22.9k★; several ship own author/version/license)

Grouped by category. Many are **script-augmented** (bundle Python tools); this is flagged in
Document 3 because it affects portability and the "reasoning vs tooling" judgment.

**Architecture / design / trade-off (C4/C5/C10/C16)** — senior-architect, tech-stack-evaluator,
migration-architect, database-designer, database-schema-designer, spec-driven-workflow,
zero-hallucination-coder, codebase-onboarding

**API / backend (C5)** — api-design-reviewer, senior-backend, sql-database-assistant

**Cloud / K8s / IaC (C13)** — aws-solution-architect, azure-cloud-architect, gcp-cloud-architect,
terraform-patterns, helm-chart-builder, kubernetes-operator, docker-development, senior-devops

**Production / SRE (C7/C11/C8)** — chaos-engineering, ship-gate, runbook-generator,
feature-flags-architect, incident-commander

**Observability (C9)** — observability-designer, slo-architect

**Security (C14)** — security-guidance, cloud-security, ai-security, senior-security, senior-secops,
red-team, security-pen-testing, threat-detection, dependency-auditor, env-secrets-manager,
secrets-vault-manager, incident-response(security)

**AI / RAG / agents (C15)** — rag-architect, agent-designer, agent-workflow-designer, agent-harness,
agenthub, mcp-server-builder, llm-cost-optimizer, prompt-governance, senior-ml-engineer,
senior-prompt-engineer

**Review (C3)** — adversarial-reviewer, named-persona-adversarial-review, pr-review-expert,
code-reviewer

**Testing (C6)** — tdd-guide, senior-qa, api-test-suite-builder, playwright-pro

**Debugging (C2)** — focused-fix

**Tech debt (C12)** — tech-debt-tracker

**CI/CD (C13)** — ci-cd-pipeline-builder

**Data engineering (C17)** — senior-data-engineer, snowflake-development

## Cluster legend (used in Document 3)

C1 design-before-code · C2 debugging/RCA · C3 code-review · C4 architecture/ADR · C5 system/API/data
design · C6 testing · C7 production-readiness/deploy · C8 incident · C9 observability · C10
trade-off · C11 chaos/failure-mode · C12 tech-debt · C13 cloud/IaC/CD · C14 security · C15
AI/LLM/agents · C16 migration · C17 data-eng · C18 docs/onboarding
