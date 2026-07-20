# Coverage Matrix — v0.1

At-a-glance view of what the 61-skill pack covers and where the gaps are, so we can fill them
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
| API Design | 🟩 | rest-api-conventions, openapi-first, problem-details-rfc9457, api-gateway-design, api-design-reviewer, hateoas | — |
| Data Modeling | 🟩 | database-designer, spring-data-jpa, data-partitioning, event-sourcing | migration-architect |
| AI Engineering / LLM | 🟨 | mcp-builder, rag-architect, agent-designer, spring-ai-integration | llm-cost-optimizer, prompt-governance |
| RAG | 🟨 | rag-architect | — |
| Security | 🟨 | code-review, spring-security-jwt, oauth2-resource-server | trailofbits/skills, agamm/owasp (repo) — dedicated review lane |
| Cloud-Native / Kubernetes / IaC (design) | 🟧 | — (operational only) | zxkane/aws-skills, terraform-patterns (de-tooled) |
| **Java / Spring** | 🟩 | 22 skills: java-architect, jpa-patterns, hexagonal-architecture, domain-driven-design, transactional-patterns, spring-data-jpa, spring-security-jwt, … (Boot 4) | — |
| **Distributed Systems** | 🟩 | microservices-patterns, service-mesh-patterns, caching-strategy, data-partitioning, api-gateway-design, system-decomposition, monolith-assessment | — |
| **Event-Driven Architecture** | 🟩 | event-driven-architecture, cqrs-design, event-sourcing | — |

## Reading the gaps

- ✅ **Done:** SRE/release/AI-eng quick wins (25 → 29), then a **Java/Spring + distributed/EDA
  round** (29 → 61): 22 Java/Spring skills (Boot 4) + 10 distributed/EDA skills. The three domains
  that were ⬜/🟧 — Java/Spring, distributed systems, event-driven — are now 🟩. Good existing skills
  existed after all; no originals needed for these.
- **Remaining gaps (next-pass, needs a repo eval):** dedicated **Security** review lane
  (trailofbits/OWASP), and **Cloud-native / Kubernetes / IaC *design*** (currently operational only).
- **Still likely original skills:** none critical — the previously-planned distributed/EDA/Java
  originals are superseded by vendored skills. Any originals now would be *personalization* (merging
  or Java-idiomatic tailoring), not gap-filling.
