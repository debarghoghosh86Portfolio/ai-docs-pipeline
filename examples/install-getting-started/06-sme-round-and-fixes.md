# Between QA rounds: SME answers, docs lead decisions, and the writer's fixes

This step is a human checkpoint. Nothing here was written by an agent. The SME answers are **constructed test material**, written to close the open questions so the release can be completed.

## SME answers (constructed), added to the source packs as new blocks

| Question | Answer | Added as |
|---|---|---|
| I-Q1 | "Users download ContosoChartsSetup.exe from the Contoso Charts download page. IT teams get it from the admin portal." | Pack 1 [S4], Pack 2 [S6] |
| I-Q2 | "Without administrator rights, setup shows 'You need administrator rights to install Contoso Charts.' and stops." | Pack 2 [S6] |
| I-Q3 | "Close PowerPoint for updates too; setup shows the same message. Versions earlier than 4.3 must be uninstalled first." | Pack 2 [S6] |
| QA-Q1 | "The update shows the same wizard pages and keeps the install location." | Pack 2 [S6] |
| I-Q6 | "In 4.4 you can't reopen the Welcome pane." | Pack 3 [S3], Pack 4 [S5] |
| QA-Q3 | "The four groups existed before 4.4. Link to Excel and the Welcome pane are new in 4.4." | Pack 3 [S3], Pack 4 [S5] |
| I-Q9 | "In the Link to Excel dialog box, select Browse to choose the workbook, then select the sheet and enter the range in the Range box, for example A1:D12. Only .xlsx workbooks are supported." | Pack 4 [S5] |

These stay open, and none of the drafts depends on them: I-Q4, I-Q5, P-Q1 (the Area chart type), and P-Q4, plus the D-Q checklist questions.

## Docs lead decisions

| Item | Decision |
|---|---|
| QA-3 vs. reviewer issue 1 (the wizard steps) | **QA is right.** A wizard page is a standard dialog task, so its choices and **Next** form one step (rule 9). The Install procedure goes back to 8 steps. **Proposed house-style change for v1.3:** add "A wizard page counts as one step: its choices and Next go together" to rule 9, so the reviewer and QA can't disagree on this again. |
| QA-9, QA-10, QA-13, QA-Q4 (link text) | One source text serves both outputs. Drafts link to **web titles**. The guide build converts links to chapter titles at publishing time. Retitling the two non-compliant web articles (W-Q1) goes to the backlog. |
| QA-5 / QA-Q2 (Welcome pane contents) | Out of scope, so the GAP is removed |
| QA-7, QA-8 (Create a chart) | The writer drafts "Add your data" from Pack 4 [S2] and adds the overview link to the intro |
| QA-2 (Choose a chart type has no Area entry) | Publish Create a chart anyway, and keep Choose a chart type on hold. The risk is noted for the publisher. |
| QA-12 (placeholder links) | Drafts use plain titles, and the publisher builds the URLs from the slug map |
| P-Q3 (What's new 4.4) | **Yes.** Add one bullet about the new installer and requirements, from Pack 1 [S1] and [S2] |
| P-Q5 (setup message in Error messages) | Not in this release. Finished chapters stay closed. |
| QA-Q5 (house-style in the QA project) | The user replaces it with v1.2 (pending) |

## The writer's fixes, applied to the drafts for QA round 2

- **System requirements:** the I-Q1 GAP is replaced with the download sentence [S4].
- **Install:**
  - the I-Q1, I-Q2, and I-Q3 GAPs and the unnumbered update GAP are filled [S6]
  - the steps are merged back to 8
- **Overview:**
  - the version phrase is scoped (only Link to Excel and the Welcome pane are new) [S3]
  - the I-Q6 GAP is filled [S3]
  - the out-of-scope GAP is removed
  - the # placeholders become plain titles
- **Create a chart:**
  - "Add your data" is drafted [S2]
  - the overview link is added to the intro
  - the I-Q6 GAP is filled [S5]
  - the D-Q1 comment is removed
- **Link a chart:**
  - steps 3–4 are rewritten from the I-Q9 answer [S5]
  - the links go back to web titles
  - the version phrase is confirmed [S5]
- **New draft:** What's new, with one 4.4 bullet [S1] [S2]
