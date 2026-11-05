# Stage 3 output: Doc drafter v6 — "Update linked chart data"

**Input:** Brief 1 from [03-doc-plan.md](03-doc-plan.md) (approved), Source pack 1 from [02-intake-output.md](02-intake-output.md), and the "Already asked" list (I-Q2, I-Q3, I-Q4, I-Q5, I-Q6, P-Q1).
**Agent:** Doc drafter v6 (`doc-drafter-v6.md`), with house-style.md
**Run:** Claude Projects, November 2026. Output copied verbatim; chat tables converted to Markdown.

The `[S#]` tags tie every sentence to a source block. `[GAP]` markers point to the question each gap is waiting on.

---

## 1. Draft

```markdown
# Update linked chart data

Refresh a linked chart to update it with the current data from its Excel workbook. [S1] Refresh is manual, so charts don't update automatically when the Excel data changes. [S1] Refresh keeps the chart's formatting, such as colors, fonts, and titles. [S1] Refresh is available in Contoso Charts 4.3 and later. [S0]

## Before you begin

- The chart must be linked to an Excel workbook (.xlsx). [S2] For more information, see Link a chart to Excel data.
- You can't refresh a chart whose data you entered in the Contoso Charts data grid. [S2]
- If the workbook is open in Excel, save it before you refresh. Refresh reads the last saved version and doesn't include unsaved changes. [S2]

## Refresh the selected chart

1. Select the chart. [S3]
2. On the **Contoso Charts** tab, in the **Data** group, select **Refresh Data**. [S3]

Tip: You can also select the chart and press Ctrl+Alt+R. [S3] [GAP: Mac shortcut — see I-Q6] For more information, see Keyboard shortcuts.

## Refresh all linked charts in a presentation

- On the **Contoso Charts** tab, in the **Data** group, select **Refresh All Charts**. Every linked chart in the presentation refreshes. [S3] [GAP: what happens to charts that aren't linked — see I-Q4]

## Messages you might see

When you refresh, you might see one of these messages. For more information, see Error messages.

| Message | Cause | What to do |
|---|---|---|
| "Can't find the linked workbook. Use Change Source to relink it." [S4] | Someone moved or deleted the linked workbook. [S4] | Relink the chart by using **Change Source**. [S4] [GAP: where Change Source is and how to use it — see I-Q2] For more information, see Fix a broken link to an Excel workbook and Change a chart's data source. |
| "Some data wasn't added because the chart is full." [S4] | The workbook has more rows than the chart has series slots. Refresh ignores the extra rows. [S4] | [GAP: how many series slots a chart has and how to include the extra rows — see I-Q3] |

## Related articles

- Link a chart to Excel data
- Fix a broken link to an Excel workbook
- Change a chart's data source
- Error messages
- Keyboard shortcuts
```

## 2. Source map

| Section | Sources used |
|---|---|
| Intro | [S0], [S1] |
| Before you begin | [S2] |
| Refresh the selected chart | [S3] |
| Refresh all linked charts in a presentation | [S3] |
| Messages you might see | [S4] |
| Related articles | Brief's "Links out" (no source facts) |

## 3. Questions for the SME

Each GAP in the draft points to an existing question: I-Q2 (Change Source), I-Q3 (series slots), I-Q4 (unlinked charts during Refresh All Charts), and I-Q6 (Mac shortcut). New questions:

- **D-Q1 (checklist):** Which operating systems does refresh support? This is related to I-Q6 but asks about overall platform support, not only the shortcut.
- **D-Q2 (checklist):** Which versions of Excel and the host app (where the presentation is open) does refresh support?
- **D-Q3 (checklist):** Does the reader need a license, role, or admin rights to refresh charts?
- **D-Q4 (checklist):** What does the reader see when a refresh completes? For example, is there a confirmation, or does the chart just update?
- **D-Q5 (checklist):** Are there other limits, such as the number of charts Refresh All Charts can handle or a maximum workbook size?
- **D-Q6 (checklist):** Are there messages other than the two in [S4]? For example, what happens if the workbook is password-protected or Excel isn't installed?
- **D-Q7:** What happens if the reader selects a data grid chart and selects Refresh Data or presses Ctrl+Alt+R? Is the button unavailable, or does a message appear?

## 4. Left out

- "Close and reopen the presentation" as a refresh method: The brief says to remove it, pending P-Q1.
- Evidence notes (R1–R5, dates, "Done, 4.3"): These are internal. The reader-facing version comes from [S0].
- A result sentence after the Refresh Data step (for example, "The chart updates with the current data"): That fact is in [S1], but the brief allows only [S3] for this heading. I left it for D-Q4 instead.
- Link URLs: No source gives them, so the Links out entries contain titles only. The writer can add the links.

> Note: the missing result sentence in step 2 was a side effect of drafter v6's rule "use only the [S#] blocks the brief lists." Drafter v7 relaxed it, and step results came back (see [06-draft-troubleshooting.md](06-draft-troubleshooting.md)).
