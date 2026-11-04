=== PART 1: PUBLISHED DOCS (Contoso Charts help, after the 4.3 release) ===

All articles cover the current version unless noted. The docs site shows one
version of each article (the latest), with version notes where behavior
differs.

--- Update linked chart data (updated 2026-11, covers 4.3 and later) ---
- "Refresh is available in Contoso Charts 4.3 and later."
- "You can't refresh a chart whose data you entered in the Contoso Charts data grid."
- "On the Contoso Charts tab, in the Data group, select Refresh Data."
- "Tip: You can also select the chart and press Ctrl+Alt+R."
- Refresh all: "Every linked chart in the presentation refreshes." [GAP: what happens to charts that aren't linked — I-Q4]
- Message table: "Can't find the linked workbook. Use Change Source to relink it." Fix: "Relink the chart by using Change Source. For more information, see Change a chart's data source."
- Message table: "Some data wasn't added because the chart is full." Fix: [GAP: series slots — I-Q3]

--- Charts don't update after editing Excel (updated 2026-11) ---
- "On the Contoso Charts tab, in the Data group, select Refresh Data."
- "To refresh every linked chart, select Refresh All Charts."
- "If someone moved or deleted the linked workbook, you see this message: 'Can't find the linked workbook. Use Change Source to relink it.' Relink the chart by using Change Source."

--- Keyboard shortcuts (updated 2026-11) ---
- Contoso Charts tab: "Ctrl+Alt+R — Refresh the selected chart's data from Excel (Contoso Charts 4.3 and later)."
- Contoso Charts tab: "Ctrl+Alt+E — Open the Export Charts to PDF dialog box."

--- Error messages (updated 2026-11) ---
- "Can't find the linked workbook. Use Change Source to relink it." — Cause: the linked workbook was moved or deleted. Fix: see Fix a broken link to an Excel workbook.
- "Some data wasn't added because the chart is full." — Cause: more rows than series slots. Fix: [GAP — I-Q3]

--- What's new in Contoso Charts (updated 2026-11) ---
- "Contoso Charts 4.3: You can now refresh linked charts with the latest data from Excel. Use Refresh Data, Refresh All Charts, or press Ctrl+Alt+R."

--- Change a chart's data source (updated 2025-02) ---
- "On the Contoso Charts tab, in the Data group, select Change Source."
- "In the Change Source dialog box, browse to the workbook, select the range, and then select OK."

--- Fix a broken link to an Excel workbook (updated 2023-01) ---
- "If a linked workbook was moved, select Change Source and browse to its new location."

--- Export charts to PDF (updated 2026-04) ---
- "You can export up to 20 charts at a time."
- "On the Contoso Charts tab, in the Export group, select Export to PDF."

--- Link a chart to Excel data (updated 2026-11) ---
- "Linked charts don't update automatically. To get the latest data, refresh the chart. For more information, see Update linked chart data."


=== PART 2: OPEN QUESTIONS FROM EARLIER STAGES ===
I-Q2: Where is Change Source, and what are the steps to relink a chart?
I-Q3: What determines how many series slots a chart has?
I-Q4: What happens to unlinked charts during Refresh All Charts?
I-Q6: Does Ctrl+Alt+R apply on all platforms (for example, Mac)?


=== PART 3: CHANGE MATERIAL SINCE THE 4.3 RELEASE ===

[C1] Contoso Charts 4.4 release notes (draft from PM, approved) — Jan 12
- "Refresh All Charts now skips charts that aren't linked and shows a summary,
  for example: 'Refreshed 5 of 7 charts. 2 charts aren't linked to a workbook.'"
- "The refresh shortcut is now Ctrl+Shift+R. Ctrl+Alt+R conflicted with a
  PowerPoint shortcut."
- "Export to PDF now supports up to 50 charts at a time."

[C2] Pull request #1044 — merged Jan 8 — "Rename Change Source to Change Data Source"
- Renames the Change Source button and dialog box to "Change Data Source".
- Updates the error message to: "Can't find the linked workbook. Use Change
  Data Source to relink it."

[C3] SME answers (email from QA lead) — Jan 15
- I-Q2: "The steps in 'Change a chart's data source' are correct, apart from
  the new button name in 4.4."
- I-Q3: "Each chart has 20 series slots. You can't add more. Split the data
  across two charts, or remove rows."
- I-Q6: "Refresh isn't available on Mac. Contoso Charts refresh is Windows
  only."

[C4] Support tickets — Dec 1 to Jan 10
- 14 tickets: "The Refresh Data button is grayed out." Support's finding: in
  every case, no chart was selected, or the chart used data-grid data.

[C5] Pull request #1050 — merged Jan 9 — "Refactor refresh engine to use async I/O"
- Internal change. No change to the UI or behavior.

[C6] Slack, #contoso-charts-dev — Jan 11
- PM: "Maybe we bring back auto-refresh in 4.5, if performance allows."

[C7] Jira CCH-1388 — "Add Refresh to the chart's right-click menu" — Status: Won't Fix
