# Document 4 — Recommended Senior Engineering Pack (v0.1)

> **Round-2 update (now 61 skills).** After confirming the priority domains had good existing skills
> we'd filtered out, a second round added **22 Java/Spring skills (Spring Boot 4)** + **10
> distributed/EDA skills** — full grid in [`../COVERAGE.md`](../COVERAGE.md). The tables below
> describe the original v0.1 core (29); the round-2 additions are catalogued in
> [`../ATTRIBUTION.md`](../ATTRIBUTION.md) and [`../README.md`](../README.md).

**29 core skills**, assembled into an installable plugin under [`../skills/`](../skills/). All are
vendored **as-is** (unchanged) from their upstream sources — per the research constraint that this
phase evaluates and assembles existing work, deferring customization. Sources, licenses, and commit
SHAs are in [`../ATTRIBUTION.md`](../ATTRIBUTION.md).

Selection philosophy: **behavior-first**. The pack is anchored on process-forcing discipline skills
(the user's stated priority) and filled out with domain skills for coverage — preferring
prose-reasoning skills over script-tool-wrappers, and never letting a single source dominate.

**Measured cost** (v0.1 core): **~2,502 tokens always-on** for 29 skills; **~4,448** for the full 61
after round 2. On-invoke cost is paid only when a skill fires.

**Source balance (core 29):** superpowers 7 · Anthropic engineering 7 · alirezarezvani 13 ·
anthropics/skills 1 · ericgandrade 1. Round-2 added: spring-boot-skills 19 · sethdford 10 · piomin 2
· jeffallan 1.

> **v0.1 update:** four skills (`slo-architect`, `feature-flags-architect`,
> `named-persona-adversarial-review`, `agent-designer`) were promoted from "deferred" after a
> second read confirmed they close the SRE/reliability, progressive-delivery, and AI-eng thin lanes.
> They are marked ⤴ in the tables below.

## The pack

Disposition is **as-is** for all 25 in v0.1 (customization deferred to the roadmap). The "future"
column flags the intended next move from [Document 5](05-personalization-roadmap.md).

### Behavior / workflow discipline (9) — the core
| Skill | Why selected / problem it solves | Future |
|---|---|---|
| systematic-debugging | Stops guess-and-check debugging; forces root cause before any fix. Solves "Root Cause Analysis." | as-is |
| zero-hallucination-coder | Grounds code in verified structure — no invented APIs/imports; opt-in for high-stakes work. | as-is |
| adversarial-reviewer | Breaks Claude's "LGTM" agreeableness with mandatory hostile-persona findings. | as-is |
| test-driven-development | Tests before code; makes "Design Before Code" concrete for bugfixes/features. | as-is |
| verification-before-completion | Kills "should work" — requires running verification + evidence before "done." | as-is |
| writing-plans | A written plan before touching code. Core "Design Before Code" behavior. | as-is |
| brainstorming | Explore requirements/options before building; reduces impulsive coding. | as-is |
| requesting-code-review | The reviewee discipline: verify work meets requirements before asking for review. | merge w/ receiving |
| receiving-code-review | Non-defensive, rigorous handling of review feedback. | merge w/ requesting |

### Architecture / system design / trade-offs (4)
| Skill | Why selected / problem it solves | Future |
|---|---|---|
| architecture | ADR discipline — decisions documented with trade-offs and consequences. | as-is |
| system-design | Service boundaries, data modeling, API design at design time. | as-is |
| senior-solution-architect | C4 modeling + DDD/Hexagonal/Clean + discovery-first. Fills the modeling gap. | as-is |
| tech-stack-evaluator | The dedicated "Trade-off Analysis" skill: weighted scoring, TCO, migration effort. | as-is |

### API / data (2)
| Skill | Why selected / problem it solves | Future |
|---|---|---|
| api-design-reviewer | REST review: convention linting, breaking-change detection, design scorecards. | as-is (script-dependent) |
| database-designer | Schema/index design, normalization, expand-contract zero-downtime migrations. | as-is |

### Production / SRE (7)
| Skill | Why selected / problem it solves | Future |
|---|---|---|
| chaos-engineering | "Failure Mode Analysis" done safely — steady-state, blast-radius, abort criteria. | as-is |
| ship-gate | Pre-prod audit that intercepts deploy intent until critical issues pass. | as-is |
| observability-designer | Metrics/logs/traces + alert-noise reduction. "Production Readiness." | as-is |
| slo-architect ⤴ | SLO/SLI discipline: Google SRE-workbook, error budgets, multi-window burn-rate, burn policy. | as-is |
| feature-flags-architect ⤴ | Flag lifecycle: rollout plans, kill switches, flag-debt, provider trade-offs. | as-is |
| deploy-checklist | Release checklist: migrations, flags, CI status, rollback triggers. | as-is |
| incident-response | Triage, severity, comms, blameless postmortem. | as-is |

### Review / debt / testing (4)
| Skill | Why selected / problem it solves | Future |
|---|---|---|
| code-review | Everyday security/perf/correctness review (N+1, injection, edge cases). | as-is |
| named-persona-adversarial-review ⤴ | Review via sourced engineer philosophies (Torvalds/Thompson/Carmack/Beck); never invent the quote. | as-is |
| tech-debt | Turns "we should refactor" into a categorized, prioritized backlog. | as-is |
| testing-strategy | Coverage and test-architecture reasoning at plan level. | as-is |

### AI / LLM engineering (3)
| Skill | Why selected / problem it solves | Future |
|---|---|---|
| mcp-builder | Build production MCP servers well — the integration surface for LLM tooling. | as-is |
| rag-architect | RAG pipeline design tied to a mandatory retrieval-eval loop; staleness-aware. | as-is |
| agent-designer ⤴ | Multi-agent architecture: supervisor/pipeline/swarm decision table, tool-schema gen. Script-dependent. | as-is |

## Coverage matrix

Behavior categories the user named × where they're covered:

| Behavior the user wants | Covered by |
|---|---|
| Design Before Code | writing-plans, brainstorming, zero-hallucination-coder, system-design |
| Architecture Review | architecture, senior-solution-architect, code-review |
| Trade-off Analysis | tech-stack-evaluator, architecture, system-design |
| Failure Mode Analysis | chaos-engineering, incident-response |
| Production Readiness | verification-before-completion, ship-gate, deploy-checklist, slo-architect, feature-flags-architect, observability-designer |
| Root Cause Analysis | systematic-debugging |
| Code Review (all sides) | code-review, adversarial-reviewer, requesting-/receiving-code-review |

Target domains × coverage:

| Domain | Coverage in v0.1 |
|---|---|
| Software Architecture / System Design | **strong** (architecture, system-design, senior-solution-architect) |
| API Design | medium (api-design-reviewer, system-design) |
| Production Engineering / SRE | **strong** (5 skills) |
| Reliability / SRE | **strong** (slo-architect, observability-designer) |
| Progressive delivery / release | **strong** (feature-flags-architect, deploy-checklist, ship-gate) |
| Observability | **strong** (observability-designer, slo-architect) |
| Testing | **strong** (testing-strategy, TDD) |
| Debugging / RCA | **strong** (systematic-debugging) |
| Review / Quality | **strong** (5 review skills) |
| AI Engineering / LLM / RAG | medium (mcp-builder, rag-architect, agent-designer) |
| Data modeling | medium (database-designer) |
| Distributed Systems / Event-driven | light — partial via system-design; **gap → roadmap** |
| Cloud-Native / Kubernetes / IaC | light — production-operational only; **gap → roadmap** |
| Java / Spring | none — deliberately (user delisted framework knowledge); **gap → roadmap** |

The gaps are intentional for an 80/20 v0.1 and are addressed in
[Document 5](05-personalization-roadmap.md).
