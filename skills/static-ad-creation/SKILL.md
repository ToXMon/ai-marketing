---
name: static-ad-creation
description: Use when making static image ads. Turns a brand URL into five researched, on-brand static ads: site style, Ad Library, Reddit pains, concepts, image generation, upload to Meta. Includes the swipe warehouse.
---

# Static-Ad Creation

One skill turns a brand URL into five researched, on-brand static ads. The whole loop runs in a hosted Claude Code harness — 100 creatives is the same process as 5.

## The flow

1. **Brand URL** — read the site: style, voice, offer, pricing, proof.
2. **Site style** — extract the visual system (colours, type, imagery) so generated ads look like the brand, not like stock AI.
3. **Ad Library** — read what competitors run on Meta/Google/LinkedIn/TikTok. What angles, hooks, and formats are live right now?
4. **Reddit pains and outcomes** — scrape what customers actually say: the pain in their words, the outcome they want. This is the copy source. No Reddit (or equivalent community) read, no ad.
5. **5 concepts** — five distinct concepts, each with hook, angle, visual direction, and copy. Different pains, different outcomes, different formats — not five versions of one idea.
6. **Image generation** — generate at 1080×1080 (and 4:5 / 9:16 variants where the placement needs them) with the image model.
7. **Upload to Meta as a new ad set** — through the ad API, with tracking (UTMs) attached. Log the upload in the experiment log.

Full prompt: `prompts/static-ad-brief.md`.

## The swipe warehouse

A standing library of creative references — ads that work, tagged by hook, format, angle, audience, and outcome. Every new brief draws on it; every result (winner or loser) goes back into it. Creative without references is guessing; with a warehouse it is remixing what already works.

Seed it with: the brand's own past winners, competitors' long-running ads (long-running = working), and the concepts that scored highest from the creative director. Tag every entry with the fields in `prompts/swipe-warehouse-entry.md`.

## Rules

- Five concepts minimum per brand per round. One concept is a guess; five is a test.
- Copy comes from customer language (Reddit, reviews, support logs), not from the model's imagination. If a headline can't be traced to something a customer said, flag it.
- Never upload without tracking. An ad without UTMs and a landing page is unmeasurable spend.
- Every ad goes to the creative director for scoring before spend (`skills/creative-direction-eval/SKILL.md`). No score, no spend.
- Record cost, impressions, and outcome per creative in `templates/ad-experiment-log.md`. The warehouse only compounds if results are written down.
