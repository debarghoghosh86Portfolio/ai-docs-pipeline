=== PART 1: INTAKE OUTPUT (from Doc intake v3) ===

Change summary
Contoso Charts 4.3 adds manual refresh for charts linked to an Excel workbook
(.xlsx). Users can refresh the selected chart or every linked chart in a
presentation from the Contoso Charts tab, or press Ctrl+Alt+R. Charts don't
update automatically. The existing article "Link a chart to Excel data"
incorrectly says charts update automatically.

Doc impact
| # | Doc | Action | Doc type | Priority | Why |
| 1 | Refresh a chart linked to Excel data | New | Task | High | New 4.3 feature |
| 2 | Link a chart to Excel data | Update | Task | High | States incorrect automatic-update behavior |
| 3 | Keyboard shortcuts reference (if one exists) | Update | Reference | Low | New shortcut Ctrl+Alt+R |
| 4 | Contoso Charts 4.3 release notes | Release note | Reference | Medium | Announces refresh |

Source pack 1: Refresh a chart linked to Excel data
Doc type: Task
Audience: Users who link charts to Excel workbooks

[S0] Version
- Available in Contoso Charts 4.3 and later. (R3, Done, 4.3)

[S1] How refresh works
- Refresh is manual. Charts don't update automatically when the Excel data changes. (R1, Oct 9)
- Refresh updates a linked chart with the current data from its Excel workbook. (R5, Oct 13)
- Chart formatting (colors, fonts, titles) is kept after refresh. (R5, Oct 13)

[S2] Requirements
- Refresh works only for charts linked to an Excel workbook (.xlsx). (R2, Oct 10)
- Charts with data typed into the Contoso Charts data grid can't be refreshed. (R2, Oct 10)
- If the linked workbook is open in Excel, refresh reads the last saved version. Unsaved changes aren't included. (R5, Oct 13)

[S3] UI and steps
- "Refresh Data" button: Data group, Contoso Charts tab. Refreshes the selected chart. (R3, Done, 4.3)
- "Refresh All Charts" button: same group. Refreshes every linked chart in the presentation. (R3, Done, 4.3)
- Ctrl+Alt+R refreshes the selected chart. (R3, Done, 4.3)

[S4] Messages and limits
- Workbook moved or deleted: "Can't find the linked workbook. Use Change Source to relink it." (R2, Oct 10)
- More rows than series slots: extra rows are ignored; warning "Some data wasn't added because the chart is full." (R5, Oct 13)

(Source packs 2–4 omitted for this test. Assume they contain the same facts.)

Intake questions
I-Q1: Which product versions does the corrected text in "Link a chart to Excel data" apply to?
I-Q2: Where is the Change Source command, and what are the steps to relink a chart?
I-Q3: What determines how many series slots a chart has?
I-Q4: What happens to unlinked charts during Refresh All Charts?
I-Q5: Is .xlsx the only supported format?
I-Q6: Does Ctrl+Alt+R apply on all platforms (for example, Mac)?
I-Q7: Does a keyboard shortcuts reference article exist, and what is its title?


=== PART 2: EXISTING DOCS INVENTORY (Contoso Charts help) ===

| TOC section | Title | Type | Last updated | Summary |
|---|---|---|---|---|
| Getting started | Install Contoso Charts | Task | 2025-06 | Install the add-in in PowerPoint. |
| Getting started | Contoso Charts overview | Concept | 2025-06 | What Contoso Charts does; the Contoso Charts tab and its groups (Create, Data, Format, Export). |
| Getting started | What's new in Contoso Charts | Reference | 2026-03 | Release notes by version. Latest entry: 4.2. |
| Create charts | Create a chart | Task | 2025-09 | Insert a chart and choose a chart type. |
| Create charts | Choose a chart type | Concept | 2025-09 | Compare chart types. |
| Create charts | Enter data in the data grid | Task | 2025-09 | Type chart data directly into the Contoso Charts data grid. |
| Work with data | Link a chart to Excel data | Task | 2024-11 | Link a chart to a range in an Excel workbook. "Your chart updates automatically when the Excel data changes." |
| Work with data | Change a chart's data source | Task | 2025-02 | Use Change Source (Data group) to point a linked chart to a different workbook or range. |
| Work with data | Update linked chart data | Task | 2021-08 | To get the latest Excel data into a linked chart, close and reopen the presentation. |
| Export and share | Export charts to PDF | Task | 2026-04 | Export one or more charts to a PDF file. |
| Reference | Keyboard shortcuts | Reference | 2025-06 | All Contoso Charts keyboard shortcuts, grouped by tab. |
| Reference | Error messages | Reference | 2025-10 | Each Contoso Charts error message, its cause, and how to fix it. |
| Troubleshooting | Charts don't update after editing Excel | Troubleshooting | 2022-05 | "This is expected. Linked charts update automatically every 5 minutes. Wait, or close and reopen the presentation." |
| Troubleshooting | Fix a broken link to an Excel workbook | Task | 2023-01 | If a linked workbook was moved, relink it with Change Source. |
