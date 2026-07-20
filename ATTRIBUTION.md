# Attribution

Every skill in `skills/` is vendored **unchanged** from an upstream open-source repository. This
pack is a *curation*, not original authorship. Each source repo's full license text is preserved in
[`licenses/`](licenses/). Skill directories retain any per-skill `LICENSE`/author metadata shipped
by their authors.

No skill files were modified during vendoring. The only pack-level file that supports a vendored
skill is `CONNECTORS.md` (carried verbatim from `anthropics/knowledge-work-plugins/engineering/` so
the Anthropic skills' optional `../../CONNECTORS.md` reference resolves).

## Source repositories

| Source repo | License | Upstream commit (as vendored) | Skills taken |
|---|---|---|---|
| [obra/superpowers](https://github.com/obra/superpowers) | MIT | `d884ae04edebef577e82ff7c4e143debd0bbec99` | systematic-debugging, test-driven-development, verification-before-completion, writing-plans, brainstorming, requesting-code-review, receiving-code-review |
| [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) | Apache-2.0 | `1a69f0ca3c77f8108dfeecf7e38262889ed0215c` | architecture, system-design, deploy-checklist, incident-response, code-review, tech-debt, testing-strategy |
| [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | MIT | `aa8d778811a557a2c28ccadda4cf3d0bd028a4cc` | zero-hallucination-coder, adversarial-reviewer, tech-stack-evaluator, api-design-reviewer, database-designer, chaos-engineering, ship-gate, observability-designer, rag-architect, slo-architect, feature-flags-architect, named-persona-adversarial-review, agent-designer |
| [anthropics/skills](https://github.com/anthropics/skills) | Apache-2.0 (per-skill `LICENSE.txt`) | `fa0fa64bdc967915dc8399e803be67759e1e62b8` | mcp-builder |
| [ericgandrade/claude-superskills](https://github.com/ericgandrade/claude-superskills) | MIT | `394587c7cb1fb249d02326c96d9735a0d5969b23` | senior-solution-architect |
| [rrezartprebreza/spring-boot-skills](https://github.com/rrezartprebreza/spring-boot-skills) | MIT | `72ed30a2a902f39607d59c3e538206804dcc2129` | (Spring Boot **4** variants) ai-observability, domain-driven-design, flyway-migrations, hateoas, hexagonal-architecture, layered-architecture, mcp-server, multi-module-maven, oauth2-resource-server, openapi-first, problem-details-rfc9457, rest-api-conventions, spring-ai-integration, spring-batch, spring-data-jpa, spring-data-redis, spring-security-jwt, testing-pyramid, transactional-patterns |
| [sethdford/claude-skills](https://github.com/sethdford/claude-skills) | MIT | `00bd9265f5a36aaaf3d50ef50efab477f50a3af3` | event-driven-architecture, cqrs-design, event-sourcing, microservices-patterns, caching-strategy, data-partitioning, api-gateway-design, service-mesh-patterns, system-decomposition, monolith-assessment |
| [piomin/claude-ai-spring-boot](https://github.com/piomin/claude-ai-spring-boot) | Apache-2.0 | `d87e7a38588a0a945ae2c11a251954897692330e` | jpa-patterns, design-patterns |
| [Jeffallan/claude-skills](https://github.com/Jeffallan/claude-skills) | MIT | `e8be415bc94d8d6ebddc2fb50e5d03c6e27d4319` | java-architect |

## Per-skill attribution

| Skill | Source repo | Upstream author (where credited) | License |
|---|---|---|---|
| systematic-debugging | obra/superpowers | obra (Jesse Vincent) | MIT |
| test-driven-development | obra/superpowers | obra | MIT |
| verification-before-completion | obra/superpowers | obra | MIT |
| writing-plans | obra/superpowers | obra | MIT |
| brainstorming | obra/superpowers | obra | MIT |
| requesting-code-review | obra/superpowers | obra | MIT |
| receiving-code-review | obra/superpowers | obra | MIT |
| architecture | anthropics/knowledge-work-plugins | Anthropic | Apache-2.0 |
| system-design | anthropics/knowledge-work-plugins | Anthropic | Apache-2.0 |
| deploy-checklist | anthropics/knowledge-work-plugins | Anthropic | Apache-2.0 |
| incident-response | anthropics/knowledge-work-plugins | Anthropic | Apache-2.0 |
| code-review | anthropics/knowledge-work-plugins | Anthropic | Apache-2.0 |
| tech-debt | anthropics/knowledge-work-plugins | Anthropic | Apache-2.0 |
| testing-strategy | anthropics/knowledge-work-plugins | Anthropic | Apache-2.0 |
| mcp-builder | anthropics/skills | Anthropic | Apache-2.0 |
| senior-solution-architect | ericgandrade/claude-superskills | ericgandrade | MIT |
| zero-hallucination-coder | alirezarezvani/claude-skills | synthesis of Ralph/GSD/Graphify/Ponytail (credited in SKILL.md) | MIT |
| adversarial-reviewer | alirezarezvani/claude-skills | ekreloff | MIT |
| tech-stack-evaluator | alirezarezvani/claude-skills | claude-code-skills | MIT |
| api-design-reviewer | alirezarezvani/claude-skills | Claude Skills Team | MIT |
| database-designer | alirezarezvani/claude-skills | claude-code-skills | MIT |
| chaos-engineering | alirezarezvani/claude-skills | claude-code-skills | MIT |
| ship-gate | alirezarezvani/claude-skills | Rajaraman Arumugam | MIT |
| observability-designer | alirezarezvani/claude-skills | claude-code-skills | MIT |
| rag-architect | alirezarezvani/claude-skills | claude-code-skills | MIT |
| slo-architect | alirezarezvani/claude-skills | claude-code-skills | MIT |
| feature-flags-architect | alirezarezvani/claude-skills | claude-code-skills | MIT |
| named-persona-adversarial-review | alirezarezvani/claude-skills | claude-code-skills | MIT |
| agent-designer | alirezarezvani/claude-skills | claude-code-skills | MIT |

> Note: `alirezarezvani/claude-skills` aggregates skills from multiple original authors; where a
> skill's own frontmatter credits a specific author (e.g. `adversarial-reviewer` → ekreloff,
> `ship-gate` → Rajaraman Arumugam) that credit is preserved in the vendored `SKILL.md`.

> **Round-2 additions (Java/Spring + distributed/EDA, 32 skills):** each maps to its source repo +
> license in the "Source repositories" table above. The 19 Spring skills come from
> `rrezartprebreza/spring-boot-skills` (**Spring Boot 4** variants); the 10 distributed/EDA skills
> from `sethdford/claude-skills`; `jpa-patterns`/`design-patterns` from `piomin/claude-ai-spring-boot`
> (author: Piotr Mińkowski); `java-architect` from `Jeffallan/claude-skills`. Per-skill author/version
> metadata is preserved in each vendored `SKILL.md` frontmatter.

## License compliance notes

- **MIT / Apache-2.0** both permit redistribution provided the copyright notice and license text
  travel with the code — satisfied via `licenses/` plus the per-skill files retained in each skill
  directory.
- **No modifications** were made to any vendored skill, so Apache-2.0's "state changes" clause is
  not triggered. If a skill is later customized (see `research/05-personalization-roadmap.md`), note
  the change in that skill's directory at that time.
- Metadata (stars, licenses, commit SHAs) in this pack was captured from the GitHub REST API and
  local `git` at vendoring time (2026-07-20), not from memory.
