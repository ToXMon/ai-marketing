---
name: creative-direction-eval
description: Use when judging creative before spend. The creative-director agent scores every ad on hook, clarity, brand fit, proof, and offer — kill or scale on the score, never on vibes. Covers trajectory vs result.
---

# Creative Direction & Evaluation

The creative-director agent scores every ad. It is the quality gate between velocity and budget: many variants go in, only scored winners get money behind them. No score, no spend.

## The scorecard

Score each creative 1–5 on each dimension, with one line of evidence per score. Template: `templates/creative-scorecard.md`. Full prompt: `prompts/creative-director-score.md`.

1. **Hook (first 3 seconds / first line).** Does it restate the viewer's pain in their words? Would they stop scrolling?
2. **Clarity.** Can a stranger say what the product is and who it's for after one look?
3. **Brand fit.** Does it look and sound like this brand — voice, visuals, offer — or like generic AI output?
4. **Proof.** Is the claim backed by something real (review, number, demo, customer language)? Unbacked claims score 1.
5. **Offer / CTA.** Is the next step obvious, single, and matched to the funnel stage?
6. **Swipe fit.** Does it remix a proven pattern from the swipe warehouse, or is it an untested guess? Guesses aren't banned — they're just scored as experiments, not as safe bets.

**Decision rule:** total 24+ = scale (fund it); 18–23 = iterate once on the weakest dimension, then re-score; under 18 = kill, log why, move on.

## Evaluate the trajectory, not just the result

An ad that converts by accident and an ad that converts because the hook, audience, and offer were right look identical in the result. Score the reasoning too: which sources did the agent use, which swipe entries did it draw on, why this angle for this persona? If the trajectory is unrecorded, the win is not repeatable — log it as luck, not learning.

## The judge is the spec

A bad judge optimises the system in the wrong direction. Before improving anything against the scorecard, prove the scorecard measures the real goal: check scored winners against actual performance weekly. If high scorers don't convert and low scorers do, fix the scorecard — don't argue with the data.

## Rules

- Score before spend, every time. No exceptions for "obvious winners."
- One iteration maximum on a mid scorer. A creative that needs three rounds of fixes is a new concept, not a revision.
- Kill fast, log the reason. The experiment log is where the learning lives; a killed ad with a reason is worth more than a live ad nobody learns from.
- Calibrate against humans: the creative director's scores get spot-checked against human review and against platform results. A judge that drifts is worse than no judge.
- The director never approves spend or publish by itself — those are human gates (see `AGENTS.md`).
