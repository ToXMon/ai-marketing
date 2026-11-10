# The Agentic Marketing System — Isenberg & Schneider

Distillation of Greg Isenberg's episode with Cody Schneider (Graphed co-founder), "AI Agents are too good at marketing now" (YouTube, 51:59). Distilled from the **full transcript** (414 auto-caption segments, supplied by the user — see `SOURCES.md`). Timestamps below refer to the episode.

Schneider's claim: a top 0.1% marketer in 2027 is not a person doing marketing tasks — it is a person building the system around agents that do them. He compares the role to a conductor, or a StarCraft player coordinating swarms. His framing for a founder's 17-year-old son with a startup and no customers: ads are one of the highest-leverage things you can do for initial traction *and* to validate an idea — and once you work this way, doing it the old way feels archaic.

## What changed

A static ad used to need a graphic designer and a copywriter. A UGC video needed a creator, a video editor, and a motion-graphics designer. Now GrokBot, Claude Code, or Dots handles that middle work with code and tokens. One agent replaces the designer, copywriter, UGC creator, editor, and motion designer — *inside the right environment*. All marketing is now code and tokens.

Long-form video editing got here faster than Schneider expected: Mirage Tesseract one-shot edits a 90-minute podcast — cutting silence and retakes, framing shots, identifying the active speaker. Work that used to be a human on a computer is now agents doing the work — but only if you give them the environment to thrive in. Schneider's metaphor: a petri dish — cozy and healthy — for the agent to live in.

## The four things an agent needs

Schneider's frame, in his own terms:

1. **Truth — a live stream of business data.** A pipeline (Airbyte) from Facebook Ads, Google Analytics, HubSpot, PostHog, and the payment processor into a warehouse (ClickHouse), constantly syncing in the background. Everything in one place, so the agent can query as often as it likes — "nuke this data warehouse with queries" — and tie an ad all the way to revenue and customer lifetime value. Never read from ad APIs directly: agents querying them flood context with massive amounts of data, hallucinate, or write their own local database full of duplicates.
2. **Hands — API keys to the stuff it should touch.** Ad accounts, CMS, CRM. An insight it cannot act on does nothing. For Facebook Ads this is the Marketing API, set up via a Notion doc in about five minutes (give the doc to your agent and it walks you through setup). **Write-only:** the API uploads creative, turns ads off, moves ads around. All data reads happen only from the warehouse. Why: agents will send thousands of requests at once against the ad APIs' terms of service and get accounts banned — Schneider's image is agents as "drunk patrons at a restaurant" / "your drunk uncle, eight Guinnesses deep." Same rule for Google Ads.
3. **A home — somewhere it can deploy code and run 24/7.** Not your laptop. A hosted Claude Code harness in the cloud. The whole UGC workflow below runs there — 100 pieces of creative is the same process as 1.
4. **Tools — image, video, and lead tools.** In the episode (names as transcribed from auto-captions): Kai AI (images/video), FAL (transcription / voice clone), OpenRouter (LLMs), Git Leads / Apollo (email and person data). Without them the agent cannot do the middle work.

Miss one and you built a chatbot. Get all four and you built a marketer. Isenberg's addition — a fifth piece, the **swipe warehouse** — is covered in its own section below.

## The Google Ads agent: what scale looks like

Schneider's canonical example of the environment paying off: an agent that runs Google Ads and, in real time, audits the search terms the account comes up for — an LLM judges whether each term's search intent is buyer-ready for the landing page it sends to, *before* money is spent. A human doing that audit on 5,000 search terms in 20 seconds is impossible. That's the scale the system operates at.

## The static-ad skill

One skill turns a brand URL into five researched, on-brand static ads. The flow, as demonstrated live:

Brand URL → site style guide extraction → Facebook Ad Library → Reddit pains and desired outcomes → 5 concepts → image generation (ChatGPT Image 2.5) → upload to Meta as a new ad set.

In the episode the command is `/static ads` + the brand URL. The skill does the work a human would do: research, then creative. Brands built live: Idea Browser, Late Checkout, Cursor, AIMÉ Leon Dore, David (protein bar), Robinhood, Teenage Engineering. You can also hand the skill a markdown brand style guide (fonts, colours) instead of relying on site extraction.

Idea Browser's five concepts, as generated on air: "Stop guessing which idea to build"; "Build what people already search for"; "Your ChatGPT ideas are generic"; "Don't waste six months on a dud"; "1,948 ideas worth building." Late Checkout's included "Your product is getting a second user. Your next product is your support ticket."; Cursor's: "Finally understand the code nobody wrote down."; David's: "Built on science, backed by doctors."

Model choice is swappable: ChatGPT Image 2.5 is the best Schneider has seen for this, but through the Kai AI unified API you can say "change this to Nano Banana" and swap models. See `skills/static-ad-creation/SKILL.md` and `prompts/static-ad-brief.md`.

## The UGC-ad skill

A UGC avatar ad with motion graphics costs about $5 — $4.75 projected for the video, plus a couple of cents for motion graphics — compared with $300–$500 from humans for a single ad. Schneider expects ~$3 with another provider. Ten ads = $50; a hundred = $500. The cost gap buys velocity, not a replacement for a real customer's voice. Sometimes the AI avatars even outperform humans reading the same script — "it just hits."

The actual pipeline, step by step as described on air (this is the part the first version of this repo got wrong — it skipped the audio and verification steps):

1. **Script** from the static-ad concepts above (`/UGC`, "write a script for this based on above").
2. **Audio first:** the script is read with a FAL voice clone → an MP3. Seedance is *not* given the script alone — left to itself it invents enunciation.
3. **Walled garden:** the MP3 + a reference image of the creator + the exact script go to Seedance together, so the avatar, voice, and words are constrained to what you supplied.
4. **V1 is 480p** (1080p costs ~$14; 480p + an ffmpeg upscale + blur gets you there cheaper). Render takes ~5 minutes.
5. **Word-by-word verification:** transcription is matched against the script to confirm an exact read. When it mispronounces a word — the episode's example is "Kalani" coming out as "Kalandla" — the transcript gives the timestamps, and the agent swaps in the correct pronunciation.
6. **Source image:** the avatar starts from a real creator's image, remixed (background, age, ethnicity changed) — explicitly not a likeness — which is what kills the plasticky Seedance look.
7. **Captions + motion graphics:** Mirage Tesseract takes the word-by-word transcription and adds captions and motion graphics, including popups and the call to action.
8. **Creative-director gate** (below) before anything goes live — including a vision-model frame-by-frame pass for alignment.

The avatar can also hold the product: provide product reference images and say so in the prompt. And there are hundreds of avatar variants available by demographic and psychographic — blue-collar, corporate office, whoever the buyer is. See `skills/ugc-ad-creation/SKILL.md` and `prompts/ugc-script.md`.

Human creators layer in through Tribe and Sideshift APIs — $40 a video in the episode's example, per-video pay plus a bonus based on spend. The script goes to creators via the API (they may modify it); the agent is the creator manager. Human-made UGC then gets the same motion-graphics treatment. Use humans when the claim needs a real person; use avatars when the variable under test is the hook, angle, or offer.

## The swipe warehouse and the creative director

Two pieces Isenberg adds:

- **A swipe warehouse of creative references.** A swipe file made sense pre-AI; now you need *thousands* of swipe files. It is the context every new brief draws on, and Isenberg calls the stored knowledge — workflows, tool usage, data usage, uploaded by the whole team — one of the most valuable things you can build. Tools mentioned for managing it: Sublime.app, and Cosmos if you want it multiplayer; Graphed has it built in.
- **A creative-director agent that scores every ad.** Isenberg's proposal on air: the director watches the 480p first pass and scores it the way CodeRabbit scores code — "don't even show me the video unless it fixes those little issues," at least an **8 or 9 out of 10**. Cody agreed on the spot and said he would ship the skill update right after the episode: a gate in the workflow — if the creative doesn't meet the quality standard, it loops back for fixes. For regulated markets (financial clients in the episode) this is already how it works: a vision model checks the creative against a can't-say list and sends it back in a recursive loop, typically resolving in 2–3 iterations. ChatGPT Image 2.5 is singled out as very good at keeping the original image rather than remixing it on each fix. And about 1 in 50 Seedance generations is still garbled nonsense — which doesn't matter at this cost.

  Greg's further suggestion: have the creative-director agent ingest David Ogilvy's books plus the 100 best YouTube/podcast episodes of the world's best creative ad people from the last 24 months, so it knows the fundamental techniques — *then* put the swipe warehouse behind it. See `skills/creative-direction-eval/SKILL.md` and `agents/creative-director.md`.

  Schneider's correction to the "one big agent" idea: don't think employees, think **jobs to be done**. You don't need a God-in-a-box to run a Facebook Ads account — Schneider says they tried that at multiple companies and it was "absolutely terrible." The better way: take what the top 1% media buyer does and turn it into code with a thinking loop on a live data stream. That is what an agent is.

## Why velocity wins: feed the beast

Facebook's algorithm (Andromeda in the episode) matches good creative to the right buyer — it is smarter than you and will show the right ad to the right person. Your job is to feed it creative velocity. Companies that shipped 10 ads a month go to 300; a typical cohort is 30. How many ads to ship depends on budget and CPL — there is a formula for it so ads actually get through testing. The episode's example: a software company ships a cohort of 30; one ad gets two demo bookings at $50 against a $150 average — then Facebook stops spending on it, because it found the two people who convert, and moves on.

And every ad is data at the cellular level: the Seedance prompt is just a JSON blob, stored in a database, tied directly to that ad's Facebook performance. At a thousand ads, that is the game — and where every company will have to be in five years to compete.

## The Graphed option — and the open-source route

Everything above can be monkey-patched together open-source (Airbyte + ClickHouse + API tokens + tool subscriptions). Or Graphed (graphed.com/platform) bundles it: data, access, tools, multiplayer (five people on different accounts through one setup), free to start. Isenberg states on air that he is not affiliated with Graphed. Cody was in San Francisco raising Graphed's seed round at recording time. This repo is not affiliated with Graphed and does not reproduce its skills — the skills here are original distillations of the described system.

Teased as follow-ups on the episode (not covered here): an outbound version (total-addressable-market map, waterfall enrichment, cold email via GrokBot) and an SEO version.
