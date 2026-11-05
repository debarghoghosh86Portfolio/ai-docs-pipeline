# Stage 3 output: Doc drafter v7 — "Charts don't update after editing Excel"

**Input:** Brief 2 from [03-doc-plan.md](03-doc-plan.md) (approved), Source pack 1 from [02-intake-output.md](02-intake-output.md), and the "Already asked" list (I-Q2, I-Q4, P-Q1, P-Q2).
**Agent:** Doc drafter v7 (`doc-drafter-v7.md`), with house-style.md v1.1 (Troubleshooting template)
**Run:** Claude Projects, November 2026. Output copied verbatim; chat tables converted to Markdown.

---

## 1. Draft

```markdown
# Charts don't update after editing Excel

This article helps you fix a linked chart that still shows old data after you edit its Excel workbook.

## Charts don't update automatically

Refresh is manual. Charts don't update automatically when the Excel data changes. [S1] Refresh is available in Contoso Charts 4.3 and later. [S0]

1. Select the chart you want to update. [S3]
2. On the **Contoso Charts** tab, in the **Data** group, select **Refresh Data**. The chart updates with the current data from its Excel workbook and keeps its formatting (colors, fonts, and titles). [S3] [S1]

You can also press Ctrl+Alt+R to refresh the selected chart. [S3] To refresh every linked chart in the presentation, on the **Contoso Charts** tab, in the **Data** group, select **Refresh All Charts**. [S3]

For more information, see Update linked chart data.

## The workbook has unsaved changes

If the linked workbook is open in Excel, refresh reads the last saved version. Unsaved changes aren't included. [S2]

1. In Excel, save the workbook. [S2]
2. In the presentation, select the chart. [S3]
3. On the **Contoso Charts** tab, in the **Data** group, select **Refresh Data**. The chart updates with the data from the saved workbook. [S3] [S1]

## The chart's data was entered in the data grid

Refresh works only for charts linked to an Excel workbook (.xlsx). [S2] Charts with data typed into the Contoso Charts data grid can't be refreshed. [S2] [GAP: how to tell whether a chart is linked to a workbook or uses the data grid] **Refresh All Charts** refreshes every linked chart in the presentation. [S3] [GAP: what happens to charts that aren't linked when you select Refresh All Charts — see I-Q4]

To fix this, link the chart to an Excel workbook. For more information, see Link a chart to Excel data.

## The workbook was moved or deleted

If the linked workbook was moved or deleted, you see this message: "Can't find the linked workbook. Use Change Source to relink it." [S4] [GAP: when the message appears, for example, when you select Refresh Data]

To fix this, relink the chart to the workbook by using **Change Source**. [S4] [GAP: Change Source steps — see I-Q2] For more information, see Fix a broken link to an Excel workbook.
```

## 2. Source map

| Section | Sources used |
|---|---|
| Title and intro | Brief (symptom) |
| Charts don't update automatically | S1 (main), S3 (main), S0 (version) |
| The workbook has unsaved changes | S2 (main), S3 and S1 (steps and result, rule 10) |
| The chart's data was entered in the data grid | S2 (main), S3 (Refresh All Charts clarification) |
| The workbook was moved or deleted | S4 (main) |

## 3. Questions for the SME

GAPs already asked: Change Source steps → I-Q2. Unlinked charts during Refresh All Charts → I-Q4.

- **D-Q1.** How can a reader tell whether a chart is linked to an Excel workbook or uses data typed into the data grid? Is there an indicator or a menu to check?
- **D-Q2.** When does the "Can't find the linked workbook" message appear? Is it when you select Refresh Data, Refresh All Charts, or when you open the presentation?
- **D-Q3 (checklist).** Which platforms does refresh support, Windows, Mac, or both? Does Ctrl+Alt+R work on Mac, or is there a different shortcut?
- **D-Q4 (checklist).** Which versions of Excel and the presentation app does refresh in Contoso Charts 4.3 support?
- **D-Q5 (checklist).** Refresh works only with .xlsx workbooks. What happens if a chart is linked to another format, like .xlsm, .xls, or .csv? Does the reader see an error message? If so, should it be another cause in this article?

> Note: D-Q3 and D-Q5 repeat intake questions I-Q6 and I-Q5, because planner v1's brief didn't list them under "Already asked." Planner v2 added a rule that every brief lists all the questions that affect its doc.

## 4. Left out

- The old article's "This is expected," "update automatically every 5 minutes," "Wait," and "close and reopen" are removed, as the brief says, pending P-Q1 and P-Q2. The "every 5 minutes" claim also contradicts S1, which says refresh is manual.
- The S4 row-limit warning ("Some data wasn't added because the chart is full.") isn't in the brief's outline. It describes a different symptom, missing data rather than old data. The docs lead might want to cover it in another troubleshooting article or a Limitations section.
- The evidence notes (R1–R5, dates, "Done") are internal.
- The source pack's doc type ("Task") is overridden by the brief, which sets Troubleshooting.
