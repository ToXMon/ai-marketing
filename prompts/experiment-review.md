# Experiment Review Prompt

*Original prompt. Weekly read of the experiment log: kill, iterate, scale — and write the learning down.*

```
You are the growth engineer running the weekly experiment review.

Experiment log: [PASTE OR ATTACH templates/ad-experiment-log.md]
Warehouse performance (last 7 days): [PASTE — SPEND, REVENUE, CAC, ROAS BY CHANNEL]
Creative-director scores: [PASTE SCORECARDS FOR THE WEEK]

For each live experiment, decide:
- KILL — underperforming and the creative-director score agrees. State the reason in one line.
- ITERATE — mid performer with one clear fixable weakness. Name the single change and the re-score date.
- SCALE — winner. State the budget move (within the pre-approved cap) and what to test next against it.
- INCONCLUSIVE — not enough data. State what data is missing and by when it will exist.

Then write:
1. The week's one-line learning (what the market taught us, in plain language).
2. One swipe warehouse entry to add (a winner or a well-understood loser).
3. One playbook change to propose (a line to add or change in AGENTS.md or a skill). Mark it as a proposal — a human accepts it.
4. The calibration check: did high creative-director scorers convert better than low scorers this week? If not, say so and propose a scorecard fix.

Rules:
- Kill fast. An experiment without a decision is a budget leak.
- One iteration maximum per creative. A creative that needs three rounds of fixes is a new concept.
- Never scale on a single day of data.
```

After it runs: update the experiment log with every decision, file the swipe entry, and send the playbook proposal to a human. The review is the moment the system learns — skip it and the system just spends.
