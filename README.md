# Senior Engineering Skill Pack

A curated pack of **29 existing, high-quality [Agent Skills](https://docs.claude.com/en/docs/claude-code/skills)**
that make Claude Code reason like a **senior / staff engineer** — design before code, analyze
trade-offs, investigate root cause, weigh failure modes, and check production readiness — rather
than adding framework trivia.

The guiding principle: **improve how Claude *thinks*, not what Claude *knows*.** Every skill here is
behavior- or reasoning-oriented. None are cheatsheets.

> **This is a curation, not original work.** All skills are vendored **unchanged** from open-source
> repositories (superpowers, Anthropic's engineering plugin, and others). Sources, licenses, and
> upstream commit SHAs are in [`ATTRIBUTION.md`](ATTRIBUTION.md); full license texts in
> [`licenses/`](licenses/).

## Install

This repo is a Claude Code **plugin marketplace** containing one plugin, `senior-engineering`.

```bash
# From an interactive `claude` session:
/plugin marketplace add isidrorn/senior-engineering-skill-pack   # or a local path to this repo
/plugin install senior-engineering@senior-engineering-skill-pack
```

Cost: **~2,502 tokens always-on** per session (the 29 skill descriptions); each skill's fuller
instructions load only when it fires. Cheap enough to keep the whole pack enabled.

> **Overlap with Anthropic's `engineering` plugin.** Seven skills here — `architecture`,
> `code-review`, `system-design`, `tech-debt`, `testing-strategy`, `deploy-checklist`,
> `incident-response` — are vendored from Anthropic's engineering plugin. If you already run that
> plugin, enable one or the other for these seven to avoid redundant copies (they're
> plugin-namespaced, so it's not a hard clash).

> **Windows note.** A few skills (`api-design-reviewer`, `tech-stack-evaluator`,
> `observability-designer`, `chaos-engineering`, `rag-architect`) bundle self-contained
> **stdlib-only** Python helpers. They run fine; on Windows, set `PYTHONIOENCODING=utf-8` so their
> Unicode output prints in the default console.

## What's inside (29 skills)

**Behavior / workflow discipline (9)** — the core
`systematic-debugging` · `zero-hallucination-coder` · `adversarial-reviewer` ·
`test-driven-development` · `verification-before-completion` · `writing-plans` · `brainstorming` ·
`requesting-code-review` · `receiving-code-review`

**Architecture / system design / trade-offs (4)**
`architecture` (ADR) · `system-design` · `senior-solution-architect` (C4/DDD) · `tech-stack-evaluator`

**API / data (2)**
`api-design-reviewer` · `database-designer`

**Production / SRE (7)**
`chaos-engineering` · `ship-gate` · `observability-designer` · `slo-architect` ·
`feature-flags-architect` · `deploy-checklist` · `incident-response`

**Review / debt / testing (4)**
`code-review` · `named-persona-adversarial-review` · `tech-debt` · `testing-strategy`

**AI / LLM engineering (3)**
`mcp-builder` · `rag-architect` · `agent-designer`

## How it was built

Five research documents record the process (discovery → inventory → evaluation → selection →
roadmap):

1. [`research/01-ecosystem-map.md`](research/01-ecosystem-map.md) — repositories surveyed, with
   API-sourced metadata
2. [`research/02-skill-inventory.md`](research/02-skill-inventory.md) — every relevant skill found
3. [`research/03-skill-evaluation.md`](research/03-skill-evaluation.md) — dedup clusters + grounded,
   quote-cited evaluation
4. [`research/04-recommended-pack.md`](research/04-recommended-pack.md) — the 25 picks, why each,
   and a coverage matrix
5. [`research/05-personalization-roadmap.md`](research/05-personalization-roadmap.md) — what to
   rewrite, merge, and add next

## Known gaps (intentional for v0.1)

Distributed-systems patterns, event-driven architecture, cloud-native/Kubernetes *design*, dedicated
security review, and Java/Spring reasoning are **light or absent** — deliberate scope for an 80/20
first cut. See the [roadmap](research/05-personalization-roadmap.md) for how they'll be filled.

## Provenance

Sources: [obra/superpowers](https://github.com/obra/superpowers) (MIT),
[anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) (Apache-2.0),
[alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) (MIT),
[anthropics/skills](https://github.com/anthropics/skills) (per-skill Apache-2.0),
[ericgandrade/claude-superskills](https://github.com/ericgandrade/claude-superskills) (MIT).
Metadata captured 2026-07-20 from the GitHub API. See [`ATTRIBUTION.md`](ATTRIBUTION.md).
