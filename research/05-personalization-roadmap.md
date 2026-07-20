# Document 5 — Personalization Roadmap

Recommendations for the **next** iteration. Nothing here is implemented yet — v0.1 deliberately
vendors existing skills unchanged. This is the backlog for turning a solid curated pack into a
personalized one, ordered by leverage.

## 1. Merges (reduce redundancy, keep the good parts)

- **requesting-code-review + receiving-code-review → one `code-review-discipline`.** They're two
  halves of the reviewee workflow and almost always relevant together. Merging saves an always-on
  description and removes a decision point.
- **Fold `spec-driven-workflow`'s one distinct idea into the planning skills.** It overlaps
  writing-plans / zero-hallucination-coder, but its Given/When/Then acceptance-criteria → test-case
  bridge is genuinely additive. Lift that section into `writing-plans` or `testing-strategy` rather
  than vendoring the whole skill.
- **Consider `ship-gate` vs `deploy-checklist` vs `verification-before-completion`.** Three
  production-readiness skills at different altitudes is defensible, but watch for the model invoking
  the wrong one; a short "which gate when" note (or a merge of ship-gate + deploy-checklist) would
  sharpen triggering.

## 2. Skills worth rewriting / de-tooling

- **De-couple the Anthropic engineering skills from connectors.** architecture, code-review,
  deploy-checklist, incident-response reference `../../CONNECTORS.md` (Slack/Jira/etc.). v0.1 carries
  that file so refs resolve, but a personalized pack should strip the connector framing for
  standalone use (Apache-2.0 requires noting the modification — see ATTRIBUTION.md).
- **Reduce script-dependence where the reasoning can stand alone.** api-design-reviewer,
  tech-stack-evaluator, observability-designer lean on bundled Python. Spot-check done:
  `api-design-reviewer`'s `api_linter.py` is **stdlib-only and functional** (produced a valid JSON
  scorecard), needing only `PYTHONIOENCODING=utf-8` for Unicode output on Windows consoles — so
  "script-dependent" here means *portable* stdlib tooling, not broken. Still, decide per skill: keep
  the scripts, or rewrite the SKILL.md so the *reasoning* works prose-only and the scripts become
  optional accelerators. The other four script-dependent skills' entrypoints are **not yet
  exercised** — verify before relying on their tool output. Aligns better with "reasoning over
  tooling."
- **`senior-solution-architect`** has a cosmetic progress-bar gimmick; the substance (C4, DDD, ADR
  formats) is worth keeping — trim the theatre.

## 3. Missing capabilities (gaps to fill from vetted sources)

Ranked by how central they are to the target domains:

1. **Distributed systems patterns** — no dedicated skill for consistency models, idempotency,
   sagas, outbox, backpressure, retries/timeouts. High value for the stated backend/distributed
   focus. Likely an original skill (see §4) or sourced from a system-design-patterns repo.
2. **Event-driven architecture** — Kafka/streaming, event sourcing, CQRS as first-class reasoning,
   not just a mention in an architecture table.
3. **Cloud-native / Kubernetes / IaC reasoning** — v0.1 covers *operating* production but not
   *designing* cloud infra. Evaluate `zxkane/aws-skills`, `hashicorp/agent-skills`, and
   alirezarezvani's own aws/azure/gcp-cloud-architect + terraform-patterns (after de-tooling).
4. **Security review** — a proper security lane. `trailofbits/skills` (CodeQL/Semgrep, high
   credibility) and `agamm/claude-code-owasp` (OWASP/ASVS) are the strongest candidates; better than
   half-including alirezarezvani's 12-skill security suite.
5. **Java / Spring reasoning** — the user delisted framework *knowledge*, but Java-idiomatic
   reasoning (concurrency pitfalls, JVM performance, Spring transaction/bean boundaries) is a
   legitimate gap given the stated stack. Candidate for an original skill grounded in the user's own
   `Claude-senior-java-engineer` curriculum (which has the material but ships no skills).
6. **Deeper SRE** — `slo-architect` and `feature-flags-architect` were **promoted into v0.1** (see
   Doc 4). `runbook-generator` (doc generator) and `migration-architect` (script-heavy, overlaps
   database-designer) remain reasonable later adds.

## 4. Opportunities for original skills

Where nothing existing is good enough and the user has a distinctive point of view:

- **`distributed-systems-review`** — a behavior skill that forces the failure-mode questions
  (what happens on partial failure? is this idempotent? what's the consistency guarantee? where's
  the backpressure?) before a distributed change ships. Nothing in the ecosystem does this as
  discipline rather than knowledge.
- **`java-spring-reasoning`** — distill the user's Java-21 curriculum into a reasoning skill (not a
  cheatsheet): when to reach for which concurrency primitive, transaction boundary pitfalls, N+1 in
  JPA, etc.
- **`design-before-code` meta-skill** — the user's list treats this as one behavior, but it's
  currently spread across brainstorming/writing-plans/zero-hallucination-coder. A thin orchestrator
  that routes to the right one by task stakes could be more usable than three separate triggers.

## 5. Process / maintenance

- **Re-pull metadata before each release.** Stars/last-push/licenses were captured 2026-07-20; the
  ecosystem churns. Re-verify from the GitHub API, not memory.
- **Pin upstream SHAs (done in ATTRIBUTION.md) and diff on update** so an upstream rewrite of a
  vendored skill is a conscious choice, not a silent drift.
- **Run `claude plugin details` after each change** to watch always-on token cost as the pack grows
  (v0.1 baseline: ~2,502 tokens for 29 skills). A senior pack that's too expensive to keep enabled
  defeats itself.
- **Complementary MCP servers, not skills.** The kubernetes/terraform/grafana MCP *servers* found
  during discovery pair well with the reasoning skills (e.g. observability-designer + mcp-grafana)
  but belong in a user's MCP config, not this pack.
