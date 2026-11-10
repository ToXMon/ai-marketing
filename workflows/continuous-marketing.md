# Continuous Marketing Workflows

Runbooks for the eight Continuous workflows. Adapted from Narasimhan's Continuous AI deck (GitHub Universe Oct 2025) — the deck names the workflows only; the marketing mapping, triggers, and outputs below are this repo's application. Every workflow has a trigger, an output, and a log. A workflow that runs but writes nothing down didn't happen.

Owner: the Continuous Marketing Operator (`agents/continuous-marketing-operator.md`).

## 1. Continuous Quality

- **Trigger:** every new asset / PR, before publish.
- **Do:** check the asset against brand voice, the claims list, and legal guardrails. Flag unbacked claims, off-voice copy, missing disclosure on AI UGC.
- **Output:** a review note (pass / fix list). Nothing publishes on a fail.
- **Log:** review notes filed per asset.

## 2. Continuous Translations

- **Trigger:** every new copy asset.
- **Do:** translate campaign copy per market and tone-check it — not just words, but idiom, offer, and cultural fit. Flag claims that don't translate (idioms, guarantees).
- **Output:** translated + tone-checked copy per market.
- **Log:** translation pairs filed with the source copy.

## 3. Continuous Accessibility

- **Trigger:** every new asset.
- **Do:** check alt text, contrast, captions, readability, and link text on every asset.
- **Output:** fixes applied or a fix list.
- **Log:** accessibility check per asset (pass / fixes).

## 4. Continuous Experiments

- **Trigger:** weekly, or on every new creative batch.
- **Do:** generate variants, launch A/B tests, read results, promote winners. Use `prompts/experiment-review.md` for the weekly read.
- **Output:** kill / iterate / scale decisions per experiment, written to `templates/ad-experiment-log.md`.
- **Log:** the experiment log is the log.

## 5. Continuous Coverage

- **Trigger:** every campaign launch.
- **Do:** verify every campaign has tracking (UTMs), a landing page, and a follow-up in place. A campaign without tracking does not launch.
- **Output:** a coverage checklist per campaign (pass / gaps).
- **Log:** checklist filed with the campaign brief.

## 6. Continuous Efficiency

- **Trigger:** hourly / daily.
- **Do:** watch CAC / ROAS across channels; reallocate or pause underperformers within the pre-approved cap.
- **Output:** reallocation / pause proposals (auto-applied only inside the cap).
- **Log:** daily efficiency note: what moved, why, and the resulting CAC/ROAS.
- **Gate:** anything above the cap, or any budget increase, needs a human.

## 7. Continuous Triage

- **Trigger:** continuous — on arrival of a reply, DM, or review.
- **Do:** classify (question / praise / complaint / refund / spam), draft a response from approved replies, escalate complaints and refunds to a human.
- **Output:** classified queue with drafts; escalations flagged.
- **Log:** triage log per item: class, action, human handoff where applicable.
- **Gate:** never auto-reply to a complaint or refund request. Draft and escalate.

## 8. Continuous Evolution

- **Trigger:** weekly review.
- **Do:** review what worked (experiment log, scores, triage themes) and propose updates to prompts, briefs, and this repo's knowledge base. One proposed change per week, maximum.
- **Output:** a playbook-change proposal (a line to add or change, with the evidence behind it).
- **Log:** proposals filed; accepted ones dated.
- **Gate:** the agent proposes; a human accepts. Nothing self-edits into the playbook.

## Rollout order

Start with one workflow (usually Triage or Quality), prove it for two weeks, then add the next. Eight at once is a migration, not a rollout.
