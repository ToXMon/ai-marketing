---
name: continuous-marketing
description: Use when setting up always-on marketing automation. Maps Narasimhan's eight Continuous AI workflows to marketing (quality, translations, accessibility, experiments, coverage, efficiency, triage, evolution) as scheduled runbooks.
---

# Continuous Marketing

Continuous AI automates judgment work on every event, in natural language: "describe to build." This skill translates Narasimhan's eight Continuous workflows (deck p. 11 — names only; the mapping below is this repo's application) into marketing runbooks. Full runbooks: `workflows/continuous-marketing.md`.

## The eight workflows

| Continuous workflow | Marketing equivalent | Trigger |
|---|---|---|
| Continuous Quality | Creative/brand review — every asset checked against brand voice, claims, legal guardrails before publish | Every new asset / PR |
| Continuous Translations | Localisation — campaign copy auto-translated and tone-checked per market as it is written | Every new copy asset |
| Continuous Accessibility | Inclusive-creative checks — alt text, contrast, captions, readability on every asset | Every new asset |
| Continuous Expts. | Ad-creative experiments — agents generate variants, launch A/B tests, read results, promote winners | Weekly, or on new creative batch |
| Continuous Coverage | Funnel coverage — agents verify every campaign has tracking, UTMs, landing page, follow-up in place | Every campaign launch |
| Continuous Efficiency | Spend optimisation — a swarm watches CAC/ROAS across channels, reallocates or pauses underperformers | Hourly / daily |
| Continuous Triage | Comment/inbox triage — agents classify replies, DMs, reviews, draft responses, escalate complaints | Continuous (on arrival) |
| Continuous Evolution | Self-improving playbook — agents review what worked, update prompts, briefs, and the knowledge base | Weekly review |

## The campaign loop

The SDLC infinity loop maps to a campaign loop: Plan (briefs/issues) → Code (asset/copy generation) → Verify (brand/legal review) → Test (pre-flight checks) → Optimize (performance tuning) → Deploy (publish/schedule) → Operate (monitor, respond, report). One agent per stage, running continuously — not a single "copilot" step.

## Platform picture (adapted from Foundry)

Models + knowledge (brand guidelines, past performance, swipe warehouse) + tools (ad platforms, analytics, MCP) + observability/evals (creative scores, experiment log, CAC/ROAS) + governance (approval gates, spend caps). The deck's proactive-security stance becomes approval and budget controls in marketing: nothing publishes and no money moves without passing a gate.

## Rules

- Every workflow has a trigger, an output, and a log. A workflow that runs but writes nothing down didn't happen.
- Triage never auto-replies to a complaint or refund request — it drafts and escalates. Routine questions may use approved replies only.
- Efficiency may pause underperformers within a pre-approved cap; anything above the cap, or any budget increase, needs a human.
- Evolution writes to the playbook only after a human accepts the proposed change. The agent proposes; the human disposes.
- Start with one workflow (usually Triage or Quality), prove it for two weeks, then add the next. Eight at once is a migration, not a rollout.
