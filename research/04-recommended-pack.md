# Document 4 — Recommended Senior Engineering Pack (v0.1)

**25 skills**, assembled into an installable plugin under [`../skills/`](../skills/). All are
vendored **as-is** (unchanged) from their upstream sources — per the research constraint that this
phase evaluates and assembles existing work, deferring customization. Sources, licenses, and commit
SHAs are in [`../ATTRIBUTION.md`](../ATTRIBUTION.md).

Selection philosophy: **behavior-first**. The pack is anchored on process-forcing discipline skills
(the user's stated priority) and filled out with domain skills for coverage — preferring
prose-reasoning skills over script-tool-wrappers, and never letting a single source dominate.

**Measured cost** (from `claude plugin details`): **~1,947 tokens always-on** per session (the 25
skill descriptions), plus on-invoke cost only when a skill actually fires. Small enough to run the
whole pack enabled.

**Source balance:** superpowers 7 · Anthropic engineering 7 · alirezarezvani 9 · anthropics/skills 1
· ericgandrade 1. Vetted/hand-crafted sources (superpowers + Anthropic) = 15 of 25.

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

### Production / SRE (5)
| Skill | Why selected / problem it solves | Future |
|---|---|---|
| chaos-engineering | "Failure Mode Analysis" done safely — steady-state, blast-radius, abort criteria. | as-is |
| ship-gate | Pre-prod audit that intercepts deploy intent until critical issues pass. | as-is |
| observability-designer | Metrics/logs/traces + SLI/SLO + alert-noise reduction. "Production Readiness." | as-is |
| deploy-checklist | Release checklist: migrations, flags, CI status, rollback triggers. | as-is |
| incident-response | Triage, severity, comms, blameless postmortem. | as-is |

### Review / debt / testing (3)
| Skill | Why selected / problem it solves | Future |
|---|---|---|
| code-review | Everyday security/perf/correctness review (N+1, injection, edge cases). | as-is |
| tech-debt | Turns "we should refactor" into a categorized, prioritized backlog. | as-is |
| testing-strategy | Coverage and test-architecture reasoning at plan level. | as-is |

### AI / LLM engineering (2)
| Skill | Why selected / problem it solves | Future |
|---|---|---|
| mcp-builder | Build production MCP servers well — the integration surface for LLM tooling. | as-is |
| rag-architect | RAG pipeline design tied to a mandatory retrieval-eval loop; staleness-aware. | as-is |

## Coverage matrix

Behavior categories the user named × where they're covered:

| Behavior the user wants | Covered by |
|---|---|
| Design Before Code | writing-plans, brainstorming, zero-hallucination-coder, system-design |
| Architecture Review | architecture, senior-solution-architect, code-review |
| Trade-off Analysis | tech-stack-evaluator, architecture, system-design |
| Failure Mode Analysis | chaos-engineering, incident-response |
| Production Readiness | verification-before-completion, ship-gate, deploy-checklist, observability-designer |
| Root Cause Analysis | systematic-debugging |
| Code Review (all sides) | code-review, adversarial-reviewer, requesting-/receiving-code-review |

Target domains × coverage:

| Domain | Coverage in v0.1 |
|---|---|
| Software Architecture / System Design | **strong** (architecture, system-design, senior-solution-architect) |
| API Design | medium (api-design-reviewer, system-design) |
| Production Engineering / SRE | **strong** (5 skills) |
| Observability | medium (observability-designer) |
| Testing | **strong** (testing-strategy, TDD) |
| Debugging / RCA | **strong** (systematic-debugging) |
| Review / Quality | **strong** (4 review skills) |
| AI Engineering / LLM / RAG | medium (mcp-builder, rag-architect) |
| Data modeling | medium (database-designer) |
| Distributed Systems / Event-driven | light — partial via system-design; **gap → roadmap** |
| Cloud-Native / Kubernetes / IaC | light — production-operational only; **gap → roadmap** |
| Java / Spring | none — deliberately (user delisted framework knowledge); **gap → roadmap** |

The gaps are intentional for an 80/20 v0.1 and are addressed in
[Document 5](05-personalization-roadmap.md).
