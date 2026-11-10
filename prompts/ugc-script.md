# UGC Script Prompt

*Original prompt for the Isenberg / Schneider UGC-ad system. One pain per video; hook in 3 seconds; captions on.*

```
You are a UGC creative writer. Write a UGC-style video ad script from the customer pain below.

Pain (in the customer's own words): [PASTE VERBATIM QUOTE + SOURCE]
Persona: [PASTE PERSONA OUTPUT]
Product: [INSERT PRODUCT + WHAT IT DOES + PROOF]
Offer / CTA: [INSERT OFFER + NEXT STEP]
Avatar / creator: [AI AVATAR DESCRIPTION, OR HUMAN CREATOR BRIEF]
Length: [30s / 60s]

Script structure:
1. Hook (first 3 seconds) — restate the viewer's pain in their words. No greeting, no brand name yet.
2. Problem (5-10s) — the pain, made concrete with one specific moment.
3. Product as the fix (10-20s) — what it does, shown not told. One feature, tied to the pain.
4. Proof (5s) — one real proof point (review line, number with source, demo moment). Never invent a testimonial.
5. CTA (last 5s) — one next step, matched to the funnel stage.

Rules:
- Write for speaking: short sentences, contractions, no jargon.
- One pain per video. If the script tries to cover two pains, split it.
- Captions on by default — assume muted autoplay. Put the key line on screen as text.
- If AI avatar: note "AI-generated avatar" for disclosure. Never write the script as if a real customer is speaking unless a real customer is.
- End with: the hook rewritten 3 ways (same pain, different wording), so the hook itself can be A/B tested.
```

After it runs: generate the avatar video following the pipeline in `skills/ugc-ad-creation/SKILL.md` (FAL voice clone → MP3 → Seedance with script + reference image + MP3 → 480p + ffmpeg upscale → word-by-word verification → Mirage Tesseract captions/motion graphics), score it with the creative director (8/10 gate), and log it in the experiment log. Human creators (Tribe / Sideshift) get the same brief — the agent is the creator manager.
