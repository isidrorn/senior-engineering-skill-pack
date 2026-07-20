# Coverage Matrix — v0.1

At-a-glance view of what the 29-skill pack covers and where the gaps are, so we can fill them
deliberately. **Strength:** 🟩 strong · 🟨 medium · 🟧 light · ⬜ none. "Best fill" names the
strongest known skill/repo to close a gap (deferred picks are already-read; repos are for a later
pass — see [research/05-personalization-roadmap.md](research/05-personalization-roadmap.md)).

## Behaviors the user named

| Behavior | | Covered by | Best fill if thin |
|---|---|---|---|
| Design Before Code | 🟩 | writing-plans, brainstorming, zero-hallucination-coder, system-design | — |
| Root Cause Analysis | 🟩 | systematic-debugging | — |
| Code Review (all sides) | 🟩 | code-review, adversarial-reviewer, named-persona-adversarial-review, requesting-/receiving-code-review | — |
| Architecture Review | 🟩 | architecture, senior-solution-architect, code-review | — |
| Trade-off Analysis | 🟨 | tech-stack-evaluator, architecture | (script-leaning; fine) |
| Failure Mode Analysis | 🟨 | chaos-engineering, incident-response | — |
| Production Readiness | 🟩 | verification-before-completion, ship-gate, deploy-checklist, observability-designer | — |

## Target domains

| Domain | | Covered by | Best fill if thin |
|---|---|---|---|
| Software Architecture / System Design | 🟩 | architecture, system-design, senior-solution-architect | — |
| Review / Quality | 🟩 | code-review, adversarial-reviewer, requesting-/receiving-code-review, tech-debt | — |
| Testing | 🟩 | testing-strategy, test-driven-development | — |
| Debugging / RCA | 🟩 | systematic-debugging | — |
| Production Engineering | 🟩 | deploy-checklist, incident-response, ship-gate, chaos-engineering | — |
| Reliability / SRE (SLO/error-budget) | 🟩 | slo-architect, observability-designer | — |
| Progressive Delivery / Release | 🟩 | feature-flags-architect, deploy-checklist, ship-gate | — |
| Observability | 🟩 | observability-designer, slo-architect | — |
| API Design | 🟨 | api-design-reviewer, system-design | (script-dependent linter) |
| Data Modeling | 🟨 | database-designer | migration-architect |
| AI Engineering / LLM | 🟨 | mcp-builder, rag-architect, agent-designer | llm-cost-optimizer, prompt-governance |
| RAG | 🟨 | rag-architect | — |
| Security | 🟧 | code-review (security lens only) | trailofbits/skills, agamm/owasp (repo) |
| Cloud-Native / Kubernetes / IaC (design) | 🟧 | — (operational only) | zxkane/aws-skills, terraform-patterns (de-tooled) |
| Distributed Systems | 🟧 | system-design (partial) | **original skill** (roadmap §4) |
| Event-Driven Architecture | ⬜ | — | **original skill** (roadmap §4) |
| Java / Spring | ⬜ | — (generic review only) | **original skill** from user's curriculum (roadmap §4) |

## Reading the gaps

- ✅ **Done (v0.1):** the SRE/release/AI-eng quick wins — `slo-architect`,
  `feature-flags-architect`, `named-persona-adversarial-review`, `agent-designer` — are now in the
  pack (25 → 29).
- **Next-pass (needs a repo eval):** dedicated Security lane (trailofbits/OWASP), Cloud-native/K8s
  *design*.
- **Original skills (nothing good enough exists):** Distributed-systems review, Event-driven
  architecture, Java/Spring reasoning.
