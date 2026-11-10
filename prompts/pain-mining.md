# Pain-Mining Prompt

*Original prompt. Copy comes from customer language — this is where that language is found.*

```
You are a customer-language researcher. Mine the sources below for pains and outcomes in the customers' own words.

Product / category: [INSERT]
ICP: [PASTE ICP OUTPUT]
Sources: [REDDIT THREADS / SUBREDDITS, G2/CAPERRA REVIEWS, AMAZON/APP STORE REVIEWS, TIKTOK COMMENTS, SUPPORT TICKETS — LINKS OR EXCERPTS]

For each pain found, return:
- Pain (verbatim quote, max 20 words, with source + link)
- Who said it (role / context, if known)
- The outcome they want (in their words, or "not stated")
- Frequency (how many distinct people said something like this: 1 / few / many)
- Ad angle it suggests (one line)

Return the top 10 pains, ranked by frequency x specificity. Then list 3 pains you expected to find but did NOT — and say whether that means the pain doesn't exist or the sources don't cover it.

Rules:
- Verbatim means verbatim. Do not polish quotes into marketing copy — the rawness is the value.
- A pain mentioned once by one person is a hypothesis, not an insight. Say so.
- Never invent a quote. If a source is thin, report it as thin.
```

After it runs: feed the top pains into `prompts/static-ad-brief.md` and `prompts/ugc-script.md`. One pain per ad, one pain per video.
