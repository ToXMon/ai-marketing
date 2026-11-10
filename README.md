# AI Marketing

Knowledge, skills, agents, and prompts for AI-enabled marketing — distilled from four sources:

1. **Katy Lee, "Prompt-Led Marketing Strategies"** (NY Tech Week, June 2025) — prompt-led ICPs, personas, and content planning.
2. **Greg Isenberg with Cody Schneider, "AI Agents are too good at marketing now"** (YouTube) — the agentic marketing system: data warehouse, platform access, tools, static ads, UGC ads, and a creative-director agent.
3. **Nitya Narasimhan (Microsoft), "Continuous AI & AI Agentic Workflows"** (AI Native Dev NYC / GitHub Universe Oct 2025) — Continuous AI: natural-language automation that runs on every repo event.
4. **Phil Knight, *Shoe Dog*** — brand storytelling: belief-first, community-first, product-as-ad.

## What's here

- `AGENTS.md` — the AI marketing engineer persona: how your coding models should run marketing as a system, not a series of one-off prompts.
- `knowledge/` — one distilled file per source. Read these before building; they carry the ideas, the limits, and what is application vs. source.
- `skills/` — ten skills, each self-contained. Load one when the task touches that area (e.g. `creative-direction-eval` before spending on an ad, `icp-building` before writing any copy).
- `agents/` — seven agent definitions: the roles in the system, what each owns, what it may touch, and where it must stop for a human.
- `prompts/` — copy-paste prompts. Katy Lee's six LEVEL UP prompts (ICP B2B/B2C, persona B2B/B2C, content roadmap, full-funnel map), plus six from the Isenberg/Schneider system (static-ad brief, UGC script, creative-director score, swipe entry, pain mining, experiment review).
- `templates/` — a campaign brief, a creative scorecard, an ad-experiment log, and an ICP/persona brief.
- `workflows/` — the eight Continuous Marketing workflows as runbooks: what runs, on what trigger, and what it must produce.

## How to use

Point a coding model at `AGENTS.md` when it sets up or runs your marketing system, or load an individual skill when the task touches that area. Start with `agentic-marketing-setup` (truth, hands, home, tools) before any agent writes a word of copy — an agent without live data and write access is a chatbot, not a marketer.

Run the prompts in order: ICP → persona → content plan → creative → score → ship or kill. Never write content without an ICP, a persona, and a real source behind it.

## The system in one paragraph

Marketing is now code and tokens: one agent replaces the designer, copywriter, UGC creator, editor, and motion designer — but only inside the right environment. That environment is live business data in a warehouse, write access to the ad platforms, a home where code runs 24/7, and tools for images, video, and leads. Inside it, agents generate creative at velocity, a creative-director agent scores every ad, humans approve spend and publish, and eight continuous workflows keep quality, experiments, triage, and the playbook itself improving without being asked.

## Sources

See `SOURCES.md` for attribution and extraction-confidence notes, including what was not verified.
