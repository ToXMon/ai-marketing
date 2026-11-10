---
name: content-planning
description: Use when turning an ICP and persona into a content plan. Covers the quarterly content roadmap (pillars, lead magnet, BOFU assets, channels) and full-funnel mapping (TOFU/MOFU/BOFU) from Katy Lee's prompts.
---

# Content Planning

Content planning is the third prompt type, and it only works after the first two: it takes the ICP and persona as inputs and returns what to make, for whom, where. A content plan written without them is a calendar, not a strategy.

## Quarterly content roadmap

Inputs: product description, ICP, sources (if any).

Outputs:

- **3 content pillar themes** — the recurring subjects the brand owns.
- **1 lead magnet idea** — the asset worth trading an email address for.
- **2 BOFU assets** — e.g. comparison page, calculator, demo video, 1-pager.
- **Recommended channels** — social, email, events, and which pillar lives where.

Full prompt: `prompts/content-roadmap.md`.

## Full-funnel mapping

Inputs: product description, ICP, persona, sources.

Map **3 core topics** across the funnel:

- **TOFU** (top): blogs, social, podcast — reach people who don't know they have the problem yet.
- **MOFU** (middle): case study, comparison, email series — help people who know the problem evaluate options.
- **BOFU** (bottom): demo video, calculator, 1-pager — give people who are ready to buy the last thing they need.

Full prompt: `prompts/content-full-funnel.md`.

## Rules

- Every topic traces back to a persona pain or driver. If you can't name whose problem a piece solves, cut it.
- One lead magnet per quarter, done well, beats four thin ones. The magnet must solve a real job the persona already does badly.
- BOFU is where revenue lives: if the roadmap has three TOFU pillars and no BOFU asset, rebalance before publishing anything.
- Channels follow the persona's trusted formats — webinars and ROI decks for the B2B ops leader, GRWM TikToks and carousels for the Gen Z skincare buyer — not the channels the team happens to like.
- The roadmap is a hypothesis. The creative-director score and the experiment log (`templates/ad-experiment-log.md`) decide what survives into next quarter.
