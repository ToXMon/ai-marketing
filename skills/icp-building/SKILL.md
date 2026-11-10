---
name: icp-building
description: Use when defining who to target. Builds B2B and B2C Ideal Customer Profiles with Katy Lee's LEVEL UP prompts, grounded in real sources, with trigger events, buying roles, and a Reason to Believe.
---

# ICP Building

The ICP defines the company or group of people you target. It informs targeting; the persona (a different skill) shapes messaging. Build the ICP first, from sources, before any copy exists.

## B2B ICP — what it must contain

1. Company type and industry
2. Company size (employees, revenue)
3. Funding stage and region
4. Business model and GTM structure
5. Core pain points this product solves
6. Common tech stack
7. Trigger events that lead to a buying decision
8. Decision-maker titles and buying roles (economic buyer, champion, end users, influencers)
9. Buying timeline and procurement considerations
10. Where, when, and how they discover or engage with vendors
11. Top 3 business priorities
12. A compelling Reason to Believe (RTB) / value proposition
13. Supporting context from G2 reviews, LinkedIn Sales Navigator, Crunchbase, win/loss notes, or support transcripts

Full prompt: `prompts/icp-b2b-level-up.md`.

## B2C ICP — what it must contain

1. Demographics (age, gender, location, income, life stage)
2. Psychographics (attitudes, lifestyle, behaviours)
3. Life priorities (convenience, wellness, fun, savings)
4. Emotional drivers (connection, confidence, joy, relief)
5. Shopping behaviours and influences
6. Media consumption habits
7. Where, when, and how they engage with brands
8. Frustrations or barriers in the category
9. Key purchase drivers (price, values, quality, trends)
10. Top 3 goals or motivations
11. Brand-positioning RTB that connects emotionally and functionally
12. Data from Amazon / Reddit / TikTok comments, reviews, trend reports (Pew, Mintel, Exploding Topics), social listening, support logs

Full prompt: `prompts/icp-b2c-level-up.md`.

## Worked reference

The deck's own LEVEL UP example (remote-workflow SaaS): 50–500 employees, Series A–C SaaS, US/Canada/UK/Australia. Pains: no centralised visibility, too many disconnected tools, async/time-zone friction, manual status updates, onboarding. Stack: Slack/Zoom/Teams, Notion/Asana/ClickUp, Drive/Dropbox, Zapier/Airtable. Triggers: rapid growth or funding round, new Head of Remote/COO hire, missed deadlines, regional expansion. Buyers: COO/Head of Ops/CFO (economic), Head of Remote/Director of Product (champion). Discovery: LinkedIn, G2/Capterra, YouTube/Google search, newsletters, SaaStr-type events.

## Rules

- Every claim in the ICP cites a source or is labelled an assumption to validate. An ICP built only from the model's priors is a persona of the model, not of the market.
- Trigger events matter more than demographics: a company that just raised, just hired an ops lead, or just missed a launch is buyable; a lookalike that didn't is not.
- Name the economic buyer separately from the champion. If you can't name who signs, the ICP is incomplete.
- One ICP per segment. A profile that fits everyone fits no one — split it and run the prompt again.
