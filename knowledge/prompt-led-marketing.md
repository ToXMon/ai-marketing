# Prompt-Led Marketing — Katy Lee (NY Tech Week, June 2025)

Distillation of Katy Lee's workshop deck, "Prompt-Led Marketing Strategies: Smarter Personas & Sharper Content" (Next Growth Wave). Lee: 20+ years in marketing consulting, brand-side, and agency; led initiatives for HP, IKEA, Hershey's; advises Fortune 500s and high-growth startups on strategy, operations, and enablement.

## The thesis

AI is a friend and partner, not a foe. Most marketing teams wear too many hats with not enough hands. Prompting is execution at the speed of thought: fail fast, fix fast, gain back time while sharpening focus and increasing output. The closing line: AI isn't a shortcut, it's your fast-forward button.

## The three prompt types

Everything in the system is one of three prompts, in this order:

1. **Ideal Customer Profile (ICP)** — the who.
2. **Persona** — the why and how.
3. **Content planning** — what you make, for whom, where.

## Good sources = good results

Great output requires great input. Prompts are only as strong as the sources behind them; garbage in = garbage out. Ground every prompt with real data.

**B2B sources:** G2 or Capterra reviews (pains and comparisons); LinkedIn comments on influencer posts; sales-call transcripts or Gong snippets; Reddit (e.g. r/sales, r/startups) for unfiltered feedback; analyst reports or trend decks (Gartner, Forrester); internal support tickets or Slack threads.

**B2C sources:** Amazon, Sephora, or App Store reviews; TikTok search or comment threads; influencer videos and community replies; Instagram story polls or Twitter threads; support chat transcripts; Google Trends and YouTube search autofill.

## ICP vs persona

- **ICP:** the company / group of people you target. WHO you target.
- **Persona:** the individual buyer (decision maker) inside that company/group. WHO you convince.
- Both are essential. ICP informs targeting; persona shapes messaging.

## Level 1 vs LEVEL UP

Every prompt type in the deck comes in two grades. Level 1 is a one-liner ("Create an Ideal Customer Profile for a SaaS product that helps remote teams manage their workflows more efficiently"). LEVEL UP assigns a role, demands a structured output, and attaches sources. The gap in output quality is the whole point: the LEVEL UP ICP for the same remote-team SaaS product returns company type, size, funding stage, business model, pain points, tech stack, trigger events, decision-maker titles, buying timeline, discovery channels, top priorities, a Reason to Believe, and supporting G2 / Sales Navigator evidence.

The six LEVEL UP prompts live in `prompts/`:

- `icp-b2b-level-up.md` — 13 outputs incl. trigger events, buying timeline, RTB.
- `icp-b2c-level-up.md` — 12 outputs incl. psychographics, emotional drivers, media habits.
- `persona-b2b-level-up.md` — 11 outputs incl. narrative workday snapshot, adoption hurdles, decision mindset.
- `persona-b2c-level-up.md` — 11 outputs incl. identity frame, influence ecosystem, vibe alignment.
- `content-roadmap.md` — quarterly roadmap: 3 pillars, 1 lead magnet, 2 BOFU assets, channels.
- `content-full-funnel.md` — 3 core topics mapped across TOFU / MOFU / BOFU.

## The six best practices

1. **Set the role.** Define who the AI is acting as (GTM strategist, SaaS copywriter).
2. **Define the goal.** Be outcome-driven ("Generate a content plan for this ICP").
3. **Provide context.** Share personas, ICPs, tone, channels.
4. **Control the format.** Ask for tables, bullet lists, or specific assets.
5. **Refine with feedback.** Improve clarity and value over iterations.
6. **Stay grounded in sources.** Add market-research results, social threads, customer pain points.

## Worked example (deck's own)

The LEVEL UP B2B ICP for a remote-workflow SaaS: 50–500 employees, Series A–C SaaS, US/Canada/UK/Australia; pains are lack of centralised visibility, too many disconnected tools, async/time-zone friction, manual status updates, onboarding; stack is Slack/Zoom/Teams + Notion/Asana/ClickUp + Drive/Dropbox + Zapier/Airtable; triggers are rapid growth or a funding round, a new Head of Remote/COO hire, missed deadlines, regional expansion; buyers are COO/Head of Ops/CFO (economic), Head of Remote/Director of Product (champion); discovery is LinkedIn, G2/Capterra, YouTube/Google search, newsletters, SaaStr-type events; RTB: "purpose-built for remote and async-first teams… it's your remote HQ" (deck's example wording, with product name as a placeholder).
