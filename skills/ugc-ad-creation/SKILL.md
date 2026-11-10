---
name: ugc-ad-creation
description: Use when making UGC-style video ads. Covers Reddit-pain scripts, AI avatar video with motion graphics (~$5 vs $300-500 human), human creators via Tribe/Sideshift, and disclosure rules.
---

# UGC-Ad Creation

A UGC avatar ad with motion graphics costs about $5, compared with $300–$500 from humans. That cost gap is the point: it buys velocity — many variants tested, fast kill/scale decisions — not a replacement for a real customer's voice.

## The flow

1. **Reddit pains** — mine the pain in customers' own words (same source discipline as static ads). The script's hook is a sentence a real person wrote, lightly edited — never invented.
2. **Script** — hook (first 3 seconds), problem, product as the fix, proof, call to action. One pain per video. Write for speaking, not reading: short sentences, contractions, no jargon.
3. **Avatar video** — generate the avatar performance from the script (image/video generation tools). Keep the avatar, setting, and product shot consistent with the brand.
4. **Motion graphics** — captions, product callouts, price/offer cards. Captions on by default: most viewers watch muted.
5. **Review** — creative-director score, then human review of the final cut before any spend or publish.

Full prompt: `prompts/ugc-script.md`.

## Human creators

Human creators layer in through Tribe and Sideshift APIs — about $40 a video plus a spend bonus, per Schneider. There the agent is the creator manager: it briefs, collects, scores, and scales human-made UGC the same way it scores AI-made UGC. Use humans when the claim needs a real person (testimonial, usage demo, regulated claim) and AI avatars when the variable under test is the hook, angle, or offer.

## Rules

- **Disclosure.** AI-avatar / synthetic-creator ads are labelled as AI-made where the platform requires it, and never presented as a real customer's words. A synthetic testimonial is a fabrication — never write one.
- **One pain per video.** A script that tries to cover three pains covers none.
- **Hook in 3 seconds.** If the first line doesn't restate the viewer's pain in their words, rewrite it.
- **Captions always on.** Assume muted autoplay.
- **Same scoring as static.** Every UGC variant goes through the creative director and the experiment log. A $5 ad that nobody watches is still wasted spend — just cheaper waste.
- **Cost honesty.** The ~$5 figure is the episode's stated cost for an avatar ad with motion graphics; verify current tool pricing before budgeting. Human-creator pricing (~$40/video + bonus) is likewise stated, not verified.
