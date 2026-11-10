---
name: ugc-ad-creation
description: Use when making UGC-style video ads. Covers Reddit-pain scripts, the full avatar pipeline (FAL voice clone, Seedance walled garden, 480p + ffmpeg upscale, word-by-word verification, Mirage Tesseract captions/motion graphics, ~$5), human creators via Tribe/Sideshift, and disclosure rules.
---

# UGC-Ad Creation

A UGC avatar ad with motion graphics costs about $5 — $4.75 projected for the video, plus a couple of cents for motion graphics — compared with $300–$500 from humans for a single ad. Schneider expects ~$3 with another provider. Ten ads = $50; a hundred = $500. That cost gap buys velocity — many variants tested, fast kill/scale decisions — not a replacement for a real customer's voice. Sometimes the AI avatars even outperform humans reading the same script.

## The pipeline

This is the pipeline as described on the episode, step by step. Don't skip steps — each one exists because the naive version fails (invented enunciation, plasticky avatars, garbled words).

1. **Script** — from the static-ad concepts (`/UGC`, "write a script for this based on above"). Hook (first 3 seconds), problem, product as the fix, proof, CTA. One pain per video. Write for speaking, not reading.
2. **Audio first** — the script is read with a FAL voice clone → an MP3. Seedance is *not* given the script alone: left to itself it invents enunciation.
3. **Walled garden** — the MP3 + a reference image of the creator + the exact script go to Seedance together, so the avatar, voice, and words are constrained to what you supplied.
4. **V1 is 480p** — 1080p costs ~$14; 480p + an ffmpeg upscale + blur gets you there cheaper. Render takes ~5 minutes. The whole workflow runs in a hosted cloud harness, not on a local machine.
5. **Word-by-word verification** — transcription is matched against the script to confirm an exact read. When it mispronounces a word (the episode's example: "Kalani" coming out as "Kalandla"), the transcript gives the timestamps and the agent swaps in the correct pronunciation.
6. **Source image** — the avatar starts from a real creator's image, remixed (background, age, ethnicity changed) — explicitly not a likeness — which kills the plasticky Seedance look.
7. **Captions + motion graphics** — Mirage Tesseract takes the word-by-word transcription and adds captions, motion graphics, popups, and the call to action.
8. **Creative-director gate** — a vision model goes through the video frame by frame for alignment before anything goes live; below 8/10 it loops back for fixes (`skills/creative-direction-eval/SKILL.md`).

The avatar can also hold the product: provide product reference images and say so in the prompt. There are hundreds of avatar variants by demographic and psychographic.

Full prompt: `prompts/ugc-script.md`.

## Human creators

Human creators layer in through Tribe and Sideshift APIs — $40 a video in the episode's example, per-video pay plus a bonus based on spend. The script goes to creators via the API (they may modify it); the agent is the creator manager: it briefs, collects, scores, and scales human-made UGC the same way it scores AI-made UGC. Human-made cuts get the same motion-graphics treatment. Use humans when the claim needs a real person (testimonial, usage demo, regulated claim) and AI avatars when the variable under test is the hook, angle, or offer.

## Rules

- **Disclosure.** AI-avatar / synthetic-creator ads are labelled as AI-made where the platform requires it, and never presented as a real customer's words. A synthetic testimonial is a fabrication — never write one.
- **One pain per video.** A script that tries to cover three pains covers none.
- **Hook in 3 seconds.** If the first line doesn't restate the viewer's pain in their words, rewrite it.
- **Captions always on.** Assume muted autoplay.
- **Same scoring as static.** Every UGC variant goes through the creative director (8/10 gate) and the experiment log. A $5 ad that nobody watches is still wasted spend — just cheaper waste.
- **Expect failures.** About 1 in 50 Seedance generations is garbled nonsense. At this cost, discard and regenerate — don't engineer around it.
- **Cost honesty.** The ~$5 figure is the episode's stated cost ($4.75 video + cents for motion graphics); verify current tool pricing before budgeting. Human-creator pricing ($40/video + spend bonus) is likewise stated, not verified.
