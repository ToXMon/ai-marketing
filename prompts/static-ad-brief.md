# Static-Ad Brief Prompt

*Original prompt for the Isenberg / Schneider static-ad system. One skill turns a brand URL into five researched, on-brand static ads.*

```
You are a performance creative strategist. Turn the brand below into 5 researched, on-brand static ad concepts.

Brand URL: [INSERT URL]
ICP: [PASTE ICP OUTPUT]
Persona: [PASTE PERSONA OUTPUT]
Offer: [INSERT OFFER + PRICE + PROOF]
Swipe warehouse entries to draw on: [PASTE 3-5 RELEVANT ENTRIES, OR "NONE YET"]

Steps:
1. Read the brand site and summarise its style, voice, offer, pricing, and proof in 5 lines.
2. Read what competitors run (Meta Ad Library / Google / TikTok) and list the 3 most common angles live right now.
3. Read customer language from the sources below and list 5 pains in the customers' own words, with the outcome each one wants.
4. Write 5 concepts. Each concept: hook (first line), angle, visual direction (layout, colours, imagery, text overlay), copy (headline + primary text + CTA), and which pain + which swipe entry it draws on. Make the 5 concepts distinct — different pains, different outcomes, different formats, not 5 versions of one idea.
5. For each concept, state the hypothesis in one sentence: "If [audience] sees [hook], they will [action] because [pain/outcome]."

Sources (Reddit threads, reviews, support logs): [INSERT LINKS OR EXCERPTS]
Format: 1080x1080 primary, with a 4:5 variant note where the placement needs it. No claim without a source — flag any headline that cannot be traced to customer language.
```

After it runs: generate the images, attach UTMs, log each creative in `templates/ad-experiment-log.md`, and send every concept to the creative director for scoring before any spend (`prompts/creative-director-score.md`).
