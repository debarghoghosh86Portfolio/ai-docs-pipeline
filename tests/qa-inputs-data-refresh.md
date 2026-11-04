=== PART 1: APPROVED DOC PLAN (excerpt) ===

Doc plan
| # | Title | Action | Doc type | TOC location |
| 1 | Update linked chart data | Rewrite | Task | Work with data |
| 2 | Charts don't update after editing Excel | Rewrite | Troubleshooting | Troubleshooting |
| 3 | Link a chart to Excel data | Update | Task | Work with data |
| 4 | Error messages | Update | Reference | Reference |
| 5 | Keyboard shortcuts | Update | Reference | Reference |
| 6 | What's new in Contoso Charts | Update | Reference | Getting started |

Existing articles that are NOT changing (valid link targets):
Change a chart's data source; Fix a broken link to an Excel workbook;
Enter data in the data grid; Contoso Charts overview.

Brief 4 (Error messages, Update): add two entries in the existing format —
"Some data wasn't added because the chart is full." and "Can't find the linked
workbook. Use Change Source to relink it." Links out: Fix a broken link to an
Excel workbook; Update linked chart data.

Brief 5 (Keyboard shortcuts, Update): add one row under the Contoso Charts tab
group: Ctrl+Alt+R refreshes the selected chart (Contoso Charts 4.3 and later).
Links out: Update linked chart data.

Brief 6 (What's new, Update): add a "Contoso Charts 4.3" entry above 4.2 that
announces manual refresh (Refresh Data, Refresh All Charts, Ctrl+Alt+R).
Links out: Update linked chart data; Keyboard shortcuts.

Link map
| From | To |
| Update linked chart data | Link a chart to Excel data |
| Update linked chart data | Fix a broken link to an Excel workbook |
| Update linked chart data | Change a chart's data source |
| Update linked chart data | Error messages |
| Update linked chart data | Keyboard shortcuts |
| Charts don't update after editing Excel | Update linked chart data |
| Charts don't update after editing Excel | Link a chart to Excel data |
| Charts don't update after editing Excel | Fix a broken link to an Excel workbook |
| Error messages | Fix a broken link to an Excel workbook |
| Error messages | Update linked chart data |
| Keyboard shortcuts | Update linked chart data |
| What's new in Contoso Charts | Update linked chart data |
| What's new in Contoso Charts | Keyboard shortcuts |


=== PART 2: SOURCE PACK 1 ===

[S0] Version
- Available in Contoso Charts 4.3 and later.

[S1] How refresh works
- Refresh is manual. Charts don't update automatically when the Excel data changes.
- Refresh updates a linked chart with the current data from its Excel workbook.
- Chart formatting (colors, fonts, titles) is kept after refresh.

[S2] Requirements
- Refresh works only for charts linked to an Excel workbook (.xlsx).
- Charts with data typed into the Contoso Charts data grid can't be refreshed.
- If the linked workbook is open in Excel, refresh reads the last saved version. Unsaved changes aren't included.

[S3] UI and steps
- "Refresh Data" button: Data group, Contoso Charts tab. Refreshes the selected chart.
- "Refresh All Charts" button: same group. Refreshes every linked chart in the presentation.
- Ctrl+Alt+R refreshes the selected chart.

[S4] Messages and limits
- Workbook moved or deleted: "Can't find the linked workbook. Use Change Source to relink it."
- More rows than series slots: extra rows are ignored; warning "Some data wasn't added because the chart is full."


=== PART 3: DRAFTS FOR THIS RELEASE ===

--- DRAFT: Update linked chart data ---

# Update linked chart data

Refresh a linked chart to update it with the current data from its Excel workbook. [S1] Refresh is manual, so charts don't update automatically when the Excel data changes. [S1] Refresh keeps the chart's formatting, such as colors, fonts, and titles. [S1] Refresh is available in Contoso Charts 4.3 and later. [S0]

## Before you begin

- The chart must be linked to an Excel workbook (.xlsx). [S2] For more information, see Link a chart to Excel data.
- You can't refresh a chart whose data you entered in the Contoso Charts data grid. [S2]
- If the workbook is open in Excel, save it before you refresh. Refresh reads the last saved version and doesn't include unsaved changes. [S2]

## Refresh the selected chart

1. Select the chart. [S3]
2. On the **Contoso Charts** tab, in the **Data** group, select **Refresh Data**. The chart updates with the current data from its workbook. [S3] [S1]

Tip: You can also select the chart and press Ctrl+Alt+R. [S3] [GAP: Mac shortcut — see I-Q6] For more information, see Keyboard shortcuts.

## Refresh all linked charts in a presentation

- On the **Contoso Charts** tab, in the **Data** group, select **Refresh All Charts**. Every linked chart in the presentation refreshes. [S3] [GAP: what happens to charts that aren't linked — see I-Q4]

## Messages you might see

| Message | Cause | What to do |
|---|---|---|
| "Can't find the linked workbook. Use Change Source to relink it." [S4] | Someone moved or deleted the linked workbook. [S4] | Relink the chart by using **Change Source**. [GAP: Change Source steps — see I-Q2] For more information, see Fix a broken link to an Excel workbook and Change a chart's data source. |
| "Some data wasn't added because the chart is full." [S4] | The workbook has more rows than the chart has series slots. [S4] | [GAP: series slots — see I-Q3] |

For more information, see Error messages.

--- DRAFT: Charts don't update after editing Excel ---

# Charts don't update after editing Excel

This article helps you fix a linked chart that still shows old data after you edit its Excel workbook.

## Charts need a manual refresh

Refresh is manual. Charts don't update automatically when the Excel data changes. [S1]

1. Select the chart you want to update. [S3]
2. On the **Contoso Charts** tab, in the **Data** group, select **Refresh Data**. The chart updates with the current data from its Excel workbook. [S3] [S1]

To refresh every linked chart, select **Refresh All**. [S3] For more information, see Refresh a chart linked to Excel data.

## The workbook has unsaved changes

Refresh reads the last saved version of the workbook and doesn't include unsaved changes. [S2]

1. In Excel, save the workbook. [S2]
2. In the presentation, select the chart, and then select **Refresh Data**. The chart updates with the saved data. [S3] [S1]

## The chart uses data from the data grid

You can't refresh charts with data entered in the Contoso Charts data grid. [S2] To fix this, link the chart to an Excel workbook. For more information, see Link a chart to Excel data.

## Someone moved or deleted the workbook

If someone moved or deleted the linked workbook, you see this message: "Can't find the linked workbook. Use Change Source to relink it." [S4] Relink the chart by using **Change Source**. [GAP: Change Source steps — see I-Q2] For more information, see Fix a broken link to an Excel workbook.

--- DRAFT: Error messages (Update: new entries only) ---

Add these two rows to the existing table, in alphabetical order:

| Message | Cause | How to fix it |
|---|---|---|
| "Can't find linked workbook. Use Change Source to relink it." [S4] | The linked workbook was moved or deleted. [S4] | Relink the chart. For more information, see Fix a broken link to an Excel workbook. |
| "Some data wasn't added because the chart is full." [S4] | The workbook has more rows than the chart has series slots. [S4] | Delete the extra rows in Excel, or split the data into two charts. |

--- DRAFT: Keyboard shortcuts (Update: new row only) ---

Add this row under "Contoso Charts tab":

| Shortcut | Action |
|---|---|
| Ctrl + Alt + R | Refresh the selected chart's data from Excel (Contoso Charts 4.3 and later). [S3] [S0] For more information, see Update linked chart data. |

--- DRAFT: What's new in Contoso Charts (Update: new 4.3 entry) ---

## Version 4.3

You can now refresh linked charts with the latest data from Excel. Use **Refresh Data** to refresh the selected chart, **Refresh All Charts** to refresh every linked chart, or press Ctrl+Alt+R. [S3] Refresh works with Excel workbooks (.xlsx) and CSV files. Charts don't update automatically. [S1]

For more information, see Refresh a chart linked to Excel data and Keyboard shortcuts.
