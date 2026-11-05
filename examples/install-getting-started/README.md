# Example run: Installation and Getting started (full-guide scope)

This is the second full run. It produced chapters 2 and 3 of the customer guide, which had no source behind them before. The outputs are real agent outputs. The raw inputs and SME answers are constructed test material.

| # | File | Stage | Headline |
|---|---|---|---|
| 01 | [01-intake-output.md](01-intake-output.md) | Intake v4 | 4 source packs, and "Needs source" applied to an uncovered topic |
| 02 | [02-doc-plan.md](02-doc-plan.md) | Planner v3 | The guide outline. It reuses 4 existing articles and finds 4 stale ones. |
| 03 | [03-drafts.md](03-drafts.md) | Drafter v7 ×5 | 0 invented facts. Every gap points to an open question. |
| 04 | [04-reviews.md](04-reviews.md) | Reviewer v5 ×5 | 8 Medium issues. Rule 7 (v1.2) applied to link text. |
| 05 | [05-qa-round1.md](05-qa-round1.md) | QA v1 | 5 Blocked. It caught a reviewer-vs-brief disagreement. |
| 06 | [06-sme-round-and-fixes.md](06-sme-round-and-fixes.md) | Human checkpoint | SME answers, docs lead decisions, and the writer's fixes |
| 07 | [07-drafts-round2.md](07-drafts-round2.md) | Writer | The drafts as sent to QA round 2 |
| 08 | [08-qa-round2.md](08-qa-round2.md) | QA v1 | Ready 4 · Ready after fixes 2 · Blocked 0 |
| 09 | [09-publisher.md](09-publisher.md) | Publisher v1 | 6 published, 1 held. It caught a patch-order bug. |
| 10 | [10-maintenance.md](10-maintenance.md) | Maintenance v2 | 3 change sets, and every trap handled |

All seven stages ran.

## Trace one fact: the Create button's name

1. **Raw input:** the old overview says "Insert Chart." The UI spec (R5) and Slack (R6) say it's "New Chart in the 4.4 build."
2. **Intake:** the decision log records Insert Chart → New Chart, and Pack 3 [S1] lists New Chart.
3. **Planner:** it flags Contoso Charts overview and Create a chart as stale because they say "Insert Chart."
4. **Drafter:** "select **New Chart**. [S1]"
5. **QA:** its terminology table shows New Chart in every draft, with "Insert Chart" only in removal comments.
6. **Guide:** chapter 3, step 1, and the label in figure 4.

The previous, hand-written guide said "Insert Chart," which shows why the rerun mattered.
