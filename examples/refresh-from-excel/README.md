# Example run: "Refresh from Excel" (Contoso Charts 4.3)

This folder contains one full run of the pipeline, with the agents' **real
outputs** at each stage. Nothing here has been rewritten or tidied. Each file
says which agent version produced it and what it was given. The only
formatting change is that tables from the chat window are converted to
Markdown.

Contoso Charts is a fictional product. The raw input is a test scenario I
wrote, with traps planted on purpose, so the results can be checked against an
answer key written before each run.

## The files, in pipeline order

| # | File | Stage | What it shows |
|---|---|---|---|
| 01 | [01-raw-input.md](01-raw-input.md) | Input | A Slack thread where the plan changes, meeting notes, a Done ticket and a Won't Fix ticket, a pull request, and a support email |
| 02 | [02-intake-output.md](02-intake-output.md) | 1. Intake | Doc impact, four source packs with evidence for every fact, a decision log, what was excluded and why, and questions I-Q1 to I-Q7 |
| 03 | [03-doc-plan.md](03-doc-plan.md) | 2. Planning | The doc plan against 14 existing articles, changes to intake's plan, seven drafting briefs, and the link map |
| 04 | [04-draft-update-linked-chart-data.md](04-draft-update-linked-chart-data.md) | 3. Drafting | A Task article with `[S#]` tags on every sentence and `[GAP]` markers pointing to open questions |
| 05 | [05-review-update-linked-chart-data.md](05-review-update-linked-chart-data.md) | 4. Review | 0 issues against 23 house-style rules, with the open GAPs listed |
| 06 | [06-draft-troubleshooting.md](06-draft-troubleshooting.md) | 3. Drafting | A Troubleshooting article: symptom title, then cause → fix sections |
| 07 | [07-review-troubleshooting.md](07-review-troubleshooting.md) | 4. Review | An issues table: 3 issues in 7 places |
| 08 | [08-qa-verdicts.md](08-qa-verdicts.md) | 5. QA | Release verdicts for six articles, a link check, a terminology table, and the questions blocking release |

## What's real and what's test material

| Item | Real agent output? | Notes |
|---|---|---|
| Raw input (01) | No: test scenario | Written by me, with six planted traps |
| Intake output (02) | ✅ Yes | Doc intake v3, given 01 exactly as shown |
| Doc plan (03) | ✅ Yes | Doc planner v1. Its input was intake's output (condensed) plus a constructed inventory of 14 existing articles |
| Drafts (04, 06) | ✅ Yes | Doc drafter v6 and v7, given the approved briefs from 03 and Source pack 1 from 02 |
| Reviews (05, 07) | ✅ Yes | Style guide reviewer v5, given the drafts from 04 and 06 |
| QA verdicts (08) | ✅ Yes | Doc QA v1. Two of its five input drafts are the real drafts above (one with two planted defects added). Three short updates were constructed with planted defects |

## Try this: trace one fact through the pipeline

Take the fact that refresh reads the last *saved* version of the workbook.

1. **Raw input (01):** the meeting notes leave it open ("Requires the linked
   workbook to be closed in Excel? Mei wasn't sure."). The pull request answers it
   three days later: "refresh reads the last SAVED version, not unsaved changes."
2. **Intake (02):** the decision log records it as resolved, and Source pack 1
   states it as a fact with its evidence: `(R5, Oct 13)`, block `[S2]`.
3. **Planning (03):** Brief 1 puts it under "Before you begin," using `[S2]`.
4. **Drafting (04):** "Refresh reads the last saved version and doesn't include
   unsaved changes. [S2]"
5. **Review (05):** no issues with the sentence.
6. **QA (08):** the fact is consistent across every draft, so it isn't flagged.

## Try this: check the traps yourself

| Trap in the raw input | Where to look | What happened |
|---|---|---|
| The plan changes from auto-refresh to manual | 02, Decision log | The final decision is used, and the earlier one is logged |
| A customer is named ("Fabrikam") | Search 02 for "Fabrikam" | Not there. It's listed under Excluded, without the name |
| A Won't Fix ticket (right-click refresh) | 02, Excluded | Excluded as not shipping |
| Speculation ("maybe," "next year") | 02, Excluded | Both excluded |
| An existing article is wrong | 02, Doc impact row 2 | Update, High priority. The reason is in "Why," not in the source pack |
| A planned "new" article already exists | 03, Changes to intake's plan | Rewritten in place instead of duplicated |
| A stale troubleshooting page intake never saw | 03, Stale content | Found and planned for a rewrite |

## What these outputs also show

The notes inside some files point out real weaknesses the runs exposed, and
the fix each one led to:

- The planner's summary miscounted its own table (fixed in planner v2).
- The drafter left out a step's result because a rule was too strict (fixed in drafter v7).
- The drafter repeated two intake questions because the brief didn't list them (fixed in planner v2).

Those are the evaluation loop at work. See the main README for every version
and what changed.
