# Document 3 — Skill Evaluation

Combines **Phase 4 (duplicate detection)** and **Phase 5 (evaluation)**. Evaluation is grounded:
every judgment below rests on the actual `SKILL.md` content that was read, and evidence quotes are
verbatim (under 15 words). Skills only structurally scanned (line count, script presence) rather
than fully read are marked *structure-only* so the basis is explicit.

## Evaluation lens

The user's guiding principle — **prefer skills that change how Claude thinks over skills that add
what Claude knows** — is the primary weight. A secondary axis emerged from reading the corpus and
matters for a *vendored* pack:

- **Behavior vs. tooling.** Some skills force a reasoning process (an "Iron Law", mandatory phases,
  a review persona). Others are wrappers around bundled Python scripts. Behavior skills are both
  higher-value per the principle *and* more portable (no scripts to break). Script-augmented skills
  can still be excellent, but they were held to a higher bar and flagged.
- **Provenance confidence.** superpowers and the Anthropic skills are hand-crafted / officially
  maintained. `alirezarezvani/claude-skills` is a 362-skill single-repo aggregation — a real
  mass-generation risk — so its picks were read individually rather than trusted on reputation.

## Phase 4 — Duplicate / overlap clusters

The unit of comparison is the **skill**, not the repo. For each cluster: the members, and the
winner(s) selected for the pack.

| Cluster | Members (source) | Decision |
|---|---|---|
| **C1 design-before-code** | writing-plans, brainstorming (superpowers); spec-driven-workflow, zero-hallucination-coder (alirezarezvani); writing-plans/brainstorming (ericgandrade, derived) | Keep **brainstorming** + **writing-plans** (superpowers originals) for the plan-first workflow, and **zero-hallucination-coder** for grounded execution. `spec-driven-workflow` overlaps → **merge candidate**, not vendored (its Given/When/Then→TDD bridge is the one distinct idea; see roadmap). Drop ericgandrade duplicates. |
| **C2 debugging / RCA** | systematic-debugging (superpowers); debug (Anthropic); focused-fix (alirezarezvani) | Keep **systematic-debugging** — the strongest behavior version. Drop Anthropic `debug` (same altitude, redundant once systematic-debugging is present) and `focused-fix`. |
| **C3 code-review** | code-review (Anthropic); requesting/receiving-code-review (superpowers); adversarial-reviewer, named-persona-adversarial-review, pr-review-expert, code-reviewer (alirezarezvani) | These occupy **different roles**, not duplicates: keep **code-review** (do the review), **requesting-** + **receiving-code-review** (reviewee discipline), **adversarial-reviewer** (hostile-persona lens). Drop `named-persona-adversarial-review` (overlaps adversarial-reviewer), `pr-review-expert`, `code-reviewer` (generic). |
| **C4 architecture / ADR** | architecture (Anthropic); senior-solution-architect (ericgandrade); senior-architect (alirezarezvani) | Keep **architecture** (concise ADR discipline) + **senior-solution-architect** (C4/DDD/Hexagonal — distinct modeling depth). Drop **senior-architect** (alirezarezvani): largely a wrapper around a diagram-generator + dependency-analyzer script — tooling, and overlaps the other two. |
| **C6 testing** | testing-strategy (Anthropic); test-driven-development (superpowers); tdd-guide, senior-qa, api-test-suite-builder (alirezarezvani) | Keep **testing-strategy** (strategy/altitude) + **test-driven-development** (the TDD discipline). Drop `tdd-guide` (dup of TDD) and the generators. |
| **C7 production-readiness** | deploy-checklist (Anthropic); ship-gate (alirezarezvani); verification-before-completion (superpowers) | Complementary altitudes — keep all three: **verification-before-completion** (done-means-verified, per-task), **deploy-checklist** (release checklist), **ship-gate** (codebase pre-prod audit that intercepts deploy intent). |
| **C8 incident** | incident-response (Anthropic); incident-commander, incident-response-security (alirezarezvani) | Keep **incident-response** (Anthropic, blameless postmortem). Drop the alirezarezvani variants (one is security-forensics-specific → roadmap security add-on). |
| **C15 AI/LLM/MCP** | mcp-builder (Anthropic); mcp-server-builder (alirezarezvani); rag-architect, agent-designer, llm-cost-optimizer… | Keep **mcp-builder** (official, Apache-2.0 confirmed — better than the alirezarezvani `mcp-server-builder` duplicate) + **rag-architect** (RAG design + eval discipline). Others → roadmap. |

## Phase 5 — Evaluation of selected skills

Rated on the behavior-vs-knowledge principle plus practical usefulness, depth, and portability.
**Tier**: DEEP-REASONING (genuine senior judgment/discipline) · SOLID (competent, pragmatic) — no
selected skill was below SOLID.

### Behavior / workflow discipline

- **systematic-debugging** *(superpowers, read-full)* — DEEP. The archetype behavior skill. Evidence:
  *"NO FIXES WITHOUT ROOT CAUSE INVESTIGATION FIRST."* Four mandatory phases, explicitly counters the
  psychology of quick-patching under pressure. Directly serves "Root Cause Analysis."
- **zero-hallucination-coder** *(alirezarezvani, read-full)* — DEEP. Discuss→Map→Decompose→Execute→
  Verify loop with KNOWN/INFERRED/UNKNOWN tagging. Notably mature: *opt-in* ("the ceremony costs more
  than it saves" for trivial edits), transparent credits to four source projects. Prose-only, portable.
- **adversarial-reviewer** *(alirezarezvani, read)* — DEEP. Three hostile personas, *"Each persona
  MUST find at least one issue — no 'LGTM' escapes."* Counters Claude's agreeableness bias in
  self-review. Prompt-only, MIT, versioned 2.9.0.
- **test-driven-development** *(superpowers, structure-only + reputation)* — SOLID/DEEP. 371 lines with
  a supporting reference; red-green-refactor as enforced discipline.
- **verification-before-completion** *(superpowers, structure-only)* — SOLID. Requires running
  verification and showing evidence before claiming done — the antidote to "should work."
- **writing-plans** / **brainstorming** *(superpowers, structure-only)* — SOLID. Plan- and
  ideation-first discipline; the "Design Before Code" behaviors the user named.
- **requesting-code-review** / **receiving-code-review** *(superpowers, structure-only)* — SOLID. The
  under-served *reviewee* side: verify-before-requesting, and non-defensive handling of feedback.

### Architecture / system design / trade-offs

- **architecture** *(Anthropic, read-head)* — DEEP. Tight ADR discipline: *"documenting a design
  decision with trade-offs and consequences."* Concise (85L) because it orchestrates rather than
  lectures. Optional connector reference (handled — see verification).
- **system-design** *(Anthropic, installed/structure)* — SOLID. Service boundaries, data modeling,
  API design at design-time altitude.
- **senior-solution-architect** *(ericgandrade, read-head)* — SOLID. C4 (Context→Component), ADRs
  (MADR/Y-Statement), Clean/Hexagonal/DDD. Evidence: *"Before proposing any change, you MUST
  understand the current state."* Fills the DDD/C4 modeling gap.
- **tech-stack-evaluator** *(alirezarezvani, read-head)* — SOLID (tooling-leaning). The dedicated
  "Trade-off Analysis" skill: weighted scoring, 5-year TCO, migration effort. Script-augmented.

### API / data

- **api-design-reviewer** *(alirezarezvani, read-head)* — SOLID (**script-dependent**). REST linting,
  breaking-change detection, design scorecards. Evidence: *"Never sign off an API review on prose
  alone — attach the tool outputs."* Value depends on its bundled Python tools; kept as the API-design
  representative, flagged accordingly.
- **database-designer** *(alirezarezvani, read-head)* — SOLID, prose. Normalization 1NF–BCNF, index
  gap analysis, expand-contract zero-downtime migrations.

### Production / SRE

- **chaos-engineering** *(alirezarezvani, read)* — DEEP. Failure-mode analysis done safely. Evidence:
  *"chaos without abort criteria is an outage."* Steady-state hypothesis, blast-radius, abort criteria.
- **ship-gate** *(alirezarezvani, read)* — SOLID, behavior. Pre-prod audit across 8 categories that
  **intercepts** deploy intent ("do NOT proceed with deployment… ask: have you run the ship gate?").
- **observability-designer** *(alirezarezvani, read)* — SOLID (tooling-leaning). Three pillars, golden
  signals, SLI/SLO; honestly defers deep error-budget math to `slo-architect`.
- **deploy-checklist** / **incident-response** *(Anthropic, installed)* — SOLID/DEEP. Release
  checklist (migrations, flags, rollback triggers) and blameless postmortem workflow.

### Review / debt / testing / AI

- **code-review** *(Anthropic, read)* — DEEP. Security/perf/correctness lens (N+1, injection, edge
  cases). One of the highest-value everyday skills.
- **tech-debt** *(Anthropic)* — SOLID. Identify/categorize/prioritize — turns "we should refactor" into
  a ranked backlog.
- **testing-strategy** *(Anthropic)* — SOLID. Coverage and test-architecture reasoning at plan level.
- **mcp-builder** *(Anthropic, read-head)* — DEEP. Building MCP servers judged by "how well they enable
  LLMs to accomplish real tasks." Apache-2.0 (per-skill license verified).
- **rag-architect** *(alirezarezvani, read-full)* — DEEP. Evidence: *"A RAG design without evaluator
  numbers is a hypothesis, not a deliverable."* Corpus-driven chunking, explicit pricing-staleness
  discipline, change-one-variable iteration.

## Notable relevant skills NOT selected (and why)

- **alirezarezvani cloud/IaC** (aws/azure/gcp-cloud-architect, terraform-patterns,
  kubernetes-operator, helm-chart-builder) — competent but **script-heavy** (e.g. terraform-patterns
  invokes scripts 13×; senior-backend 30×), less portable and more tooling than reasoning. Deferred;
  the cloud-native gap is documented in the roadmap.
- **alirezarezvani security suite** (~12 skills: red-team, threat-detection, senior-security…) — a
  whole security domain of its own; better sourced from a specialist repo (trailofbits, OWASP) in a
  later security-focused iteration than half-included now.
- **slo-architect, migration-architect, feature-flags-architect, runbook-generator** — strong SOLID
  skills that would extend production coverage; held back to keep v0.1 at ~25 and avoid overweighting
  one source. Top candidates for the next expansion.
- **anthropics/skills claude-api, webapp-testing** — claude-api is knowledge-reference (not behavior);
  webapp-testing is a Playwright tool. Neither fits the behavior-first thesis.
