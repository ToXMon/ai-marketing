# Continuous AI & Agentic Workflows — Narasimhan (Microsoft)

Distillation of Nitya Narasimhan's deck, "Continuous AI & AI Agentic Workflows: Using Natural Language Programming for Repository Automation Actions" (AI Native Dev NYC Meetup; GitHub Universe Oct 2025 talk/demo). Starting point for all agentic workflows in the deck: **gh.io/gh-aw** (Jonathan "Peli" De Halleux).

## The CI → Continuous AI shift

The deck's core argument is a parallel to CI/CD. Continuous Integration automated build/test on every commit with rules. Continuous AI automates *judgment work* on every repo event — but in natural language instead of rules. The shorthand: **"describe to build"** — describe the desired automation in prose, and an agent workflow performs it.

- **Old:** single model, simple POCs, point-in-time ROI; deterministic logic features; manual coding → building → testing; reactive monitoring, human-driven deployment, multiple point-based security solutions.
- **New:** next-gen AI platform — multi-model, automated agentic workflows, continuous improvement; AI-agentic DevOps — adaptive reasoning agents; the work loop reframed as writing prompts → creating → evaluation; proactive security and governance — ongoing predictive observability, dynamic AI-driven orchestration, end-to-end platform-based security.

The developer's unit of work shifts from writing code to writing prompts, creating, and evaluating.

## The eight Continuous workflows

The GitHub Universe Oct 2025 demo set. The deck names them only — the one-liners below are plain-language glosses of the names:

1. **Continuous Quality** — agents review every change for quality, continuously.
2. **Continuous Translations** — agents localise content as it lands, rather than in batches.
3. **Continuous Accessibility** — agents check every change for accessibility barriers.
4. **Continuous Expts. (Doodle Jump)** — agents run ongoing experiments; "Doodle Jump" is the demo app used as the experiment subject.
5. **Continuous Coverage (Tests)** — agents keep test coverage up as code changes.
6. **Continuous Efficiency (Swarms)** — swarms of agents optimise for cost/performance.
7. **Continuous Triage (Bug fixes)** — agents triage incoming issues and fix bugs.
8. **Continuous Evolution (Agent Q)** — agents improve the system itself over time; "Agent Q" is the named demo agent.

## The end-to-end platform picture (Microsoft Foundry)

AI development needs end-to-end support, in a six-step cycle: (1) app and agent orchestration, (2) frontier & OSS models, (3) knowledge and tools, (4) observability and agent controls, (5) fine-tuning and customisation, (6) deployment to local and edge. Foundry is positioned as covering all six — "Simple / Trusted / Powerful". Its three core capabilities for developers: **models, agents, dev tools.**

The detailed capability map (deck p. 9, partially legible): model choice spanning OSS, frontier, small, multimodal, and industry models with intelligent routing; agent knowledge grounded on your data via RAG, agentic retrieval, and live-web data; agents built as declarative / hosted / multi-agent workflows with built-in memory, agent controls, and channel integration; tools via pre-built and MCP tools, open protocols, and your own tool catalog; deployment anywhere (local/on-device and cloud); observability via tracing, evaluations, monitoring, quality/safety/security, and cost/throughput; built-in enterprise security and governance (network isolation, AI gateway, agent identity, AI red teaming, access controls, data classification/encryption, policies, compliance).

## Agents across the SDLC

An infinity-loop diagram places agents at every lifecycle stage: Plan (create issues, brainstorm, Spec Kit) → Code (agent mode, coding agent, Spark workbench) → Verify (code quality, code review, autofix) → Test → Optimize (app modernisation, SRE agent) → Deploy (migration, Spark runtime, deployment) → Operate (support, investigate, metrics). Agents are not a single "copilot" step; they are a standing crew, one per stage, running continuously.

## GitHub Next / Spark

GitHub Next is the long-term-bets lab ("investigates the future of software development," projects from "napkin sketch … to product"), with four projects shown: Project Copernicus (LLM-powered codebase navigation, napkin sketch, Jul 2025), Continuous AI (LLM-powered automation in platform-based software collaboration, WIP, Jun 2025), GitHub Spark (product, Oct 2024), and Agentic Workflows (research prototype, Aug 2025). **GitHub Spark** lets anyone create and share micro-apps from a natural-language description on a fully managed runtime — the deck's example prompt builds a "#30DaysOfMicrosoftFoundry" site (hero panel + searchable/sortable/filterable card gallery, one card per day).

## How this maps to marketing (repo author's application)

The deck is about software repos. The marketing translation — each Continuous workflow as a marketing workflow, and the SDLC loop as a campaign loop (Plan = briefs, Code = asset generation, Verify = brand/legal review, Test = pre-flight checks, Optimize = performance tuning, Deploy = publish, Operate = monitor/respond/report) — is this repo's proposal, not the deck's claim. It lives in full in `workflows/continuous-marketing.md` and `skills/continuous-marketing/SKILL.md`. Spark is the model for marketer-facing micro-apps: "describe the campaign, get the landing page."
