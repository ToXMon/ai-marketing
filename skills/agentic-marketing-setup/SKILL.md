---
name: agentic-marketing-setup
description: Use before any agent does marketing work. Sets up Cody Schneider's four requirements — truth (live data warehouse), hands (write access), home (24/7 host), tools — plus the API-completeness buying rule and the code-over-no-code rule.
---

# Agentic Marketing Setup

An agent is code plus a live data stream plus a model called only at judgment points. Before any agent writes copy, makes an ad, or sends outreach, all four requirements below must be in place. Miss one and you built a chatbot.

## 1. Truth — a live stream of business data

Pipe Facebook Ads, Google Analytics, HubSpot/CRM, and the payment processor into a warehouse (e.g. Airbyte → ClickHouse) every hour. Everything in one place, so the agent can query as often as it likes and tie an ad all the way to revenue and customer lifetime value.

Rules:

- Agents read **only** from the warehouse. Never paste a CSV into a prompt.
- Never let an agent query ad APIs directly: it floods context, hallucinates, or builds its own local database full of duplicates.
- Freshness is a spec: state the refresh cadence (hourly) and the newest data timestamp in every report. Stale truth is not truth.

## 2. Hands — write access to the things it should touch

Ad accounts, CMS, CRM. An insight the agent cannot act on does nothing. Grant the narrowest write access that lets the agent complete its job (create ad sets, publish scheduled posts, update CRM records), and log every write.

## 3. A home — somewhere code runs 24/7

Not your laptop. A hosted Claude Code harness / cloud host on a schedule, with logs, retries, and a stop condition. If it only runs when someone's machine is awake, it is a demo, not a system.

## 4. Tools — image, video, and lead tools

Image/video generation, transcription, LLM access, enrichment, and scrapers that read what customers say on Reddit. Without them the agent cannot do the middle work. The episode's stack: Kai AI (images/video), FAL (transcription), OpenRouter (LLMs), Git Leads / Apollo (email and person data). Substitute equivalents freely — the requirement is the capability, not the brand.

## Buying and building rules

- **API completeness.** "Can I do everything through the API that I can do in the UI?" If not, the tool is off the list, however good it looks.
- **Code over no-code.** When the cost of code is ~0, skip the Zapier/n8n middle layer and go straight to code; build the exact internal view just-in-time instead of buying a widget for every process.
- **The model judges; the code works.** Write down the skilled human's routine first, turn it into scripts on a schedule, and call the model only where a judgment is needed. Everything else is software the coding agent writes for you.
- **Graphed as a reference, not a dependency.** Schneider's Graphed platform bundles data, access, and tools with a free start. The open-source route (pipeline + warehouse + host + tools, above) works too. This repo is not affiliated with Graphed and does not reproduce its skills.

## Setup checklist

- [ ] Warehouse receiving hourly from ads, analytics, CRM, payments
- [ ] Agent service account with narrow write access to ad platforms + CMS/CRM
- [ ] Hosted runner with schedule, logs, and a kill switch
- [ ] Image, video, transcription, enrichment tools connected and keyed
- [ ] Swipe warehouse seeded (see `skills/static-ad-creation/SKILL.md`)
- [ ] Human approval gates configured for spend, publish, and claims (see `AGENTS.md`)
