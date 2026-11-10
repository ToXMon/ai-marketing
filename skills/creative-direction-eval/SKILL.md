---
name: creative-direction-eval
description: Use when judging creative before spend. The creative-director agent scores every ad out of 10 — 8+ to show/ship, below 8 loops back for fixes. Covers the vision-model frame-by-frame pass, the regulated-market recursive loop, and trajectory vs result.
---

# Creative Direction & Evaluation

The creative-director agent scores every ad. It is the quality gate between velocity and budget: many variants go in, only scored winners get money behind them. No score, no spend. Isenberg's framing on the episode: the director watches the 480p first pass and scores it the way CodeRabbit scores code — "don't even show me the video unless it fixes those little issues" — at least an **8 or 9 out of 10**.

## The scorecard

Score each creative out of 10 overall, judging it on six dimensions (1–5 each, one line of evidence per score). The dimensions inform the score; the gate is the overall number. Template: `templates/creative-scorecard.md`. Full prompt: `prompts/creative-director-score.md`.

1. **Hook (first 3 seconds / first line).** Does it restate the viewer's pain in their words? Would they stop scrolling?
2. **Clarity.** Can a stranger say what the product is and who it's for after one look?
3. **Brand fit.** Does it look and sound like this brand — voice, visuals, offer — or like generic AI output?
4. **Proof.** Is the claim backed by something real (review, number, demo, customer language)? Unbacked claims pull the score down hard.
5. **Offer / CTA.** Is the next step obvious, single, and matched to the funnel stage?
6. **Swipe fit.** Does it remix a proven pattern from the swipe warehouse, or is it an untested guess? Guesses aren't banned — they're scored as experiments, not as safe bets.

For video, a vision model also goes through the output frame by frame for alignment (captions, motion graphics, CTA placement) before scoring.

**Decision rule:** 8–10 = show to a human and ship; 5–7 = one loop of fixes on the weakest dimension, then re-score; under 5 = kill, log why, move on.

## The recursive loop (regulated markets)

For regulated markets (financial clients in the episode), the loop is explicit: a vision model checks the creative against a can't-say / can't-promise list and sends it back for changes, repeating until it passes — typically resolving in 2–3 iterations. ChatGPT Image 2.5 is singled out as very good at keeping the original image intact through fixes rather than remixing it each time. Use this loop anywhere a claim, promise, or compliance rule is at stake — not just in finance.

## What the director is made of

Greg's suggestion on the episode: have the creative-director agent ingest David Ogilvy's books plus the 100 best YouTube/podcast episodes of the world's best creative ad people from the last 24 months, so it knows the fundamental techniques — then put the swipe warehouse behind it. A director with no taste library is just a rubric; the books, the episodes, and the warehouse are the taste.

## Evaluate the trajectory, not just the result

An ad that converts by accident and an ad that converts because the hook, audience, and offer were right look identical in the result. Score the reasoning too: which sources did the agent use, which swipe entries did it draw on, why this angle for this persona? If the trajectory is unrecorded, the win is not repeatable — log it as luck, not learning.

## The judge is the spec

A bad judge optimises the system in the wrong direction. Before improving anything against the scorecard, prove the scorecard measures the real goal: check scored winners against actual performance weekly. If high scorers don't convert and low scorers do, fix the scorecard — don't argue with the data.

## Rules

- Score before spend, every time. No exceptions for "obvious winners."
- One loop of fixes maximum on a mid scorer (5–7). A creative that needs three rounds of fixes is a new concept, not a revision — except in the regulated-market loop, where 2–3 iterations are the norm.
- Kill fast, log the reason. The experiment log is where the learning lives; a killed ad with a reason is worth more than a live ad nobody learns from.
- Calibrate against humans: the creative director's scores get spot-checked against human review and against platform results. A judge that drifts is worse than no judge.
- The director never approves spend or publish by itself — those are human gates (see `AGENTS.md`).
- Cody's note from the episode: the gate as a workflow step (score → loop → ship) was announced as a skill update to ship right after recording. Treat the workflow as described, not as verified-shipped.
