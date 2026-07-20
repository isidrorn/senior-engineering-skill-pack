# Project Status & Continuation Guide

**Read this first when resuming.** It captures where the pack stands, the decisions that govern it,
what's next, and the operational gotchas — so a fresh session can pick up without re-deriving context.

_Last updated: 2026-07-20 (end of round 2). State snapshots below are hypotheses once time passes —
cheap-check them (`git log`, `claude plugin details`) before trusting._

## What this is

A Claude Code **plugin marketplace** (one plugin, `senior-engineering`) of curated, **vendored-as-is**
Agent Skills that make Claude reason like a senior/staff engineer. Curation — not original authorship.
All work is committed and pushed to `main` (repo: `isidrorn/senior-engineering-skill-pack`).

## Current state

- **61 skills** in [`skills/`](skills/) — verified: `claude plugin validate .` passes, installs, all 61
  enumerate, ~**4,448 always-on tokens**, no name collisions.
- **9 source repos**, licenses captured in [`licenses/`](licenses/), attributed with commit SHAs in
  [`ATTRIBUTION.md`](ATTRIBUTION.md).
- Built in two rounds: v0.1 core (29) → round 2 added 22 Java/Spring (Boot 4) + 10 distributed/EDA (61).

### Resume reading order
1. **This file** — decisions + next steps + gotchas.
2. [`COVERAGE.md`](COVERAGE.md) — at-a-glance domain/behavior grid; the 🟧/open rows are the work.
3. [`research/05-personalization-roadmap.md`](research/05-personalization-roadmap.md) — the backlog.
4. [`FINDINGS.md`](FINDINGS.md) — useful out-of-scope discoveries (unused repos, MCP servers).
5. [`research/04-recommended-pack.md`](research/04-recommended-pack.md) — the pack rationale.

## Decisions locked (don't re-litigate; from user feedback)

- **No skill-count cap.** "~30" was a rough estimate; 61 is fine, so is more. Coverage + trigger
  quality decide the number, not a quota. Don't defer a good skill to hit a number.
- **Pragmatic license stance.** Copy anything useful from public repos; attribute it (SHA + license
  text). Only avoid clearly/explicitly-protected content. Don't exclude on license purism.
- **Java/Spring-heavy is intentional** — the maintainer's stack. Prefer Java-tailored skills over
  great-but-other-language ones. Java *reasoning* is in-scope; only generic cheatsheets aren't.
- **Behavior > tooling, but essence-extract not discard.** Script-heavy skills weren't dropped for
  being good — their reasoning gets mined into prose in the customization round (roadmap §3b).
- **Flag out-of-scope finds** in `FINDINGS.md` rather than losing them.
- **Git: push to `main` freely, no branches** until we need to compare alternative approaches.
- **Reason about intent, don't over-literalize** rules/numbers. Ask when unsure.

(These live in memory too: project `skillpack-curation-preferences`, `git-workflow-commit-to-main`;
global `reason-about-intent-not-literal`, `user-java-spring-engineer`.)

## What's next (pick up here)

Open gaps + backlog, roughly prioritized. **Security was parked by the user; nothing is urgent.**

1. **Security review lane** (🟨→🟩) — evaluate `trailofbits/skills` (CodeQL/Semgrep) + `agamm/claude-code-owasp`. Flagged in FINDINGS.
2. **Cloud-native / Kubernetes / IaC *design*** (🟧) — currently operational-only. Candidates: `zxkane/aws-skills`, `hashicorp/agent-skills`, alirezarezvani cloud skills (need de-tooling).
3. **Customization round** (roadmap §1–§3b) — merge `requesting-`+`receiving-code-review`; essence-extract script-heavy skills to prose; de-couple Anthropic skills from connectors.
4. **`jvm-concurrency-performance`** — the one Java sub-area the vendored Spring skills don't cover; candidate original skill.
5. **Deepen from diverse sources** — `sethdford` has ~245 more skills; `alirezarezvani` ~40 more in-scope (see FINDINGS / inventory).

## Operational gotchas (important for a fresh session)

- **Clones are gone.** Round-1/2 source repos were cloned into an *ephemeral session scratchpad* (not
  in this repo). To add/modify skills you must **re-clone** the source repos — URLs + pinned SHAs are
  in [`ATTRIBUTION.md`](ATTRIBUTION.md). Clone into a scratch dir, never into the repo.
- **No `gh` CLI** in this environment. Get repo metadata (stars/last-push/license) via **GitHub REST
  API** — PowerShell `Invoke-RestMethod https://api.github.com/repos/OWNER/REPO` (raw, no summarizer)
  or `WebFetch`. Re-pull before trusting any star/date — the ecosystem churns and knowledge is stale.
- **Verify a change** with the throwaway-config trick (doesn't touch real config):
  ```bash
  export CLAUDE_CONFIG_DIR=<scratch>/throwaway-config
  claude plugin validate .
  claude plugin marketplace add <repo-path>
  claude plugin install senior-engineering@senior-engineering-skill-pack
  claude plugin details senior-engineering   # confirms skill count + always-on token cost
  ```
- **Subagents stalled repeatedly** this session (stream watchdog, ~600s no-progress). Prefer doing
  grounded reads yourself; if delegating, keep scope tiny (1–2 repos) and expect failures.
- **Vendoring rule:** copy **whole skill directories** (scripts/references travel), not just SKILL.md.
  Check frontmatter-`name` uniqueness across the whole pack before copying (collisions break the pack).
  Spring skills exist in Boot 3 **and** 4 with identical names — we vendored **Boot 4**.
- **Windows:** script-dependent skills print Unicode; run their Python with `PYTHONIOENCODING=utf-8`.
- **Benign noise:** `git add` shows LF→CRLF warnings — harmless (autocrlf normalization).

## Structure
```
skills/            61 vendored skill dirs (one plugin, auto-discovered)
.claude-plugin/    plugin.json + marketplace.json
licenses/          9 upstream LICENSE texts
research/          01 ecosystem · 02 inventory · 03 evaluation · 04 pack · 05 roadmap
ATTRIBUTION.md · COVERAGE.md · FINDINGS.md · README.md · PROJECT-STATUS.md (this) · CONNECTORS.md
```
