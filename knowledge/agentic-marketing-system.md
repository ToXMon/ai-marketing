# The Agentic Marketing System — Isenberg & Schneider

Distillation of Greg Isenberg's episode with Cody Schneider (Graphed co-founder), "AI Agents are too good at marketing now" (YouTube). Schneider's claim: a top 0.1% marketer in 2027 is not a person doing marketing tasks — it is a person building the system around agents that do them. He compares the role to a conductor, or a StarCraft player coordinating swarms.

## What changed

A static ad used to need a graphic designer and a copywriter. A UGC video needed a creator, a video editor, and a motion-graphics designer. Now GrokBot, Claude Code, or Codex handles that middle work with code and tokens. One agent replaces the designer, copywriter, UGC creator, editor, and motion designer — *inside the right environment*. All marketing is now code and tokens.

## The four things an agent needs

Schneider's frame, in his own terms:

1. **Truth — a live stream of business data.** A pipeline (Airbyte) from Facebook Ads, Google Analytics, HubSpot, and the payment processor into a warehouse (ClickHouse), refreshed hourly. Everything in one place, so the agent can query as often as it likes and tie an ad all the way to revenue and customer lifetime value. Never read from ad APIs directly: agents querying them flood their context, hallucinate, or build their own local database full of duplicates.
2. **Hands — API keys to the stuff it should touch.** Ad accounts, CMS, CRM. An insight it cannot act on does nothing.
3. **A home — somewhere it can deploy code and run 24/7.** Not your laptop. A hosted Claude Code harness in the cloud.
4. **Tools — image, video, and lead tools.** In the episode: Kai AI (images/video), FAL (transcription), OpenRouter (LLMs), Git Leads / Apollo (email and person data). Without them the agent cannot do the middle work.

Miss one and you built a chatbot. Get all four and you built a marketer.

## The static-ad skill

One skill turns a brand URL into five researched, on-brand static ads. The flow, as described in the episode and Schneider's public summary:

Brand URL → site style → Ad Library (what competitors run) → Reddit pains and outcomes → 5 concepts → image generation (e.g. GPT Image) → upload to Meta as a new ad set.

In the episode they build static ads live for Idea Browser, Late Checkout, Cursor, and more. The whole loop runs in a hosted Claude Code harness — 100 creatives is the same process as 5. See `skills/static-ad-creation/SKILL.md` and `prompts/static-ad-brief.md`.

## The UGC-ad skill

A UGC avatar ad with motion graphics costs about $5, compared with $300–$500 from humans. The flow: Reddit pain points → script → avatar video → motion graphics → review. See `skills/ugc-ad-creation/SKILL.md` and `prompts/ugc-script.md`.

Human creators layer in through Tribe and Sideshift APIs — about $40 a video plus a spend bonus, per Schneider. There the agent is the creator manager, not the creator.

## The swipe warehouse and the creative director

Two pieces Isenberg adds:

- **A swipe warehouse of creative references.** A standing library of ads that work, tagged by hook, format, angle, and outcome — the context every new brief draws on. Creative without references is guessing; with a warehouse it is remixing what already works.
- **A creative-director agent that scores every ad.** Every generated ad gets scored before spend. The director is the quality gate between velocity and budget: many variants go in, only scored winners get money behind them. See `skills/creative-direction-eval/SKILL.md` and `agents/creative-director.md`.

## Why velocity wins

Facebook's algorithm matches good creative to the right buyer. Creative velocity — many tested variants, fast kill/scale decisions — is the leverage. The durable lesson from Schneider's earlier episode (same system, applied to lead-finding): an agent is code plus a live data stream plus a model called only at judgment points, built by writing down the skilled human's routine first. The model judges; the code does the work.

## Software buying rule (Schneider)

API completeness: "can I do everything through the API that I can do in the UI?" If not, the tool is off the list, however good it looks. And when the cost of code is ~0, skip the no-code middle layer (Zapier/n8n) and go straight to code; build the exact internal view just-in-time instead of buying a widget for every process.

## What this repo does with it

This repo does **not** reproduce Cody's skills (his linked skills URL was a shortened link that was not resolved, and his repo was not read). It distils the described system into original skills, agents, and prompts in the same shape — so a coding agent given `AGENTS.md` can set up truth/hands/home/tools and run the static-ad, UGC-ad, and creative-director loops.
