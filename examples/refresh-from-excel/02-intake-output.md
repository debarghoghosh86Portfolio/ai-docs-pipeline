# Stage 1 output: Doc intake v3

**Input:** [01-raw-input.md](01-raw-input.md)
**Agent:** Doc intake v3 (`intake-agent-v3.md`)
**Run:** Claude Projects, November 2026. Output copied verbatim; chat tables converted to Markdown.

---

## 1. Change summary

Contoso Charts 4.3 adds manual refresh for charts linked to an Excel workbook (.xlsx). Users can refresh the selected chart or every linked chart in the presentation from the Data group on the Contoso Charts tab, or refresh the selected chart with a keyboard shortcut. Refresh keeps chart formatting, reads the last saved version of the workbook, and shows messages when the workbook can't be found or the chart can't hold all the new data. This affects anyone who links charts to Excel data, and it means an existing article that says charts update automatically needs to be corrected.

## 2. Doc impact

| # | Doc | Action | Doc type | Audience | Priority | Why |
|---|---|---|---|---|---|---|
| 1 | Refresh a chart linked to Excel data | New | Task | Users who link charts to Excel workbooks | High | New feature; users can't find or use refresh without it. Support reports customers asking why charts don't update when Excel changes. |
| 2 | Link a chart to Excel data | Update | Task | Users who link charts to Excel workbooks | High | The article claims charts update automatically, which is incorrect. Support requested this fix for the 4.3 release. |
| 3 | Contoso Charts 4.3 release notes | Release note | Reference | All Contoso Charts users | Medium | Announces the new refresh feature in 4.3. |
| 4 | Keyboard shortcuts (existing reference, if any) | Update | Reference | All Contoso Charts users | Low | New shortcut added in 4.3. Existence and title of this article are unconfirmed (I-Q7). |

## 3. Source packs

### Doc 1: Refresh a chart linked to Excel data

```
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
- If the linked workbook is open in Excel, refresh reads the last saved version of the workbook. Unsaved changes aren't included. (R5, Oct 13)

[S3] UI and steps
- "Refresh Data" button: in the Data group on the Contoso Charts tab. Refreshes the selected chart. (R2, Oct 10; R3, Done, 4.3)
- "Refresh All Charts" button: in the Data group on the Contoso Charts tab. Refreshes every linked chart in the presentation. (R2, Oct 10; R3, Done, 4.3)
- Keyboard shortcut: Ctrl+Alt+R refreshes the selected chart. (R3, Done, 4.3)

[S4] Messages and limits
- If the linked workbook has moved or been deleted, this message appears: "Can't find the linked workbook. Use Change Source to relink it." (R2, Oct 10)
- If the new data has more rows than the chart has series slots, the extra rows are ignored and this warning appears: "Some data wasn't added because the chart is full." (R5, Oct 13)

Already asked (don't repeat):
- I-Q2: Where is Change Source, and what are the steps to relink?
- I-Q3: What determines a chart's series slots, and can users increase them?
- I-Q4: What happens to unlinked charts during Refresh All Charts, and what do the buttons do when nothing or an unlinked chart is selected?
- I-Q5: Are file types other than .xlsx supported (.xlsm, .xls, .csv)?
- I-Q6: Does Ctrl+Alt+R apply on all platforms (for example, Mac)?
```

### Doc 2: Link a chart to Excel data

```
Doc type: Task
Audience: Users who link charts to Excel workbooks

[S0] Version
- Refresh for linked charts is available in Contoso Charts 4.3 and later. (R3, Done, 4.3)
- Version scope of the corrected text is unconfirmed (see I-Q1).

[S1] Incorrect statement to remove
- The current article says "Your chart updates automatically when the Excel data changes." This is incorrect. (R6, Oct 14)

[S2] Correct behavior
- Refresh is manual. Charts don't update automatically when the Excel data changes. (R1, Oct 9)
- To update a linked chart, use "Refresh Data" (selected chart) or "Refresh All Charts" (every linked chart in the presentation) in the Data group on the Contoso Charts tab. (R2, Oct 10; R3, Done, 4.3)
- If the linked workbook is open in Excel, refresh reads the last saved version. Unsaved changes aren't included. (R5, Oct 13)

Already asked (don't repeat):
- I-Q1: Which product versions does the corrected text apply to?
- I-Q2: Where is Change Source, and what are the steps to relink?
```

### Doc 3: Contoso Charts 4.3 release notes

```
Doc type: Reference
Audience: All Contoso Charts users

[S0] Version
- Available in Contoso Charts 4.3 and later. (R3, Done, 4.3)

[S1] New feature: refresh linked charts
- Charts linked to an Excel workbook (.xlsx) can be refreshed with the current data from the workbook. (R2, Oct 10; R5, Oct 13)
- Refresh is manual. (R1, Oct 9)
- "Refresh Data" refreshes the selected chart; "Refresh All Charts" refreshes every linked chart in the presentation. Both are in the Data group on the Contoso Charts tab. (R2, Oct 10; R3, Done, 4.3)
- Ctrl+Alt+R refreshes the selected chart. (R3, Done, 4.3)
- Chart formatting (colors, fonts, titles) is kept after refresh. (R5, Oct 13)

Already asked (don't repeat):
- I-Q5: Are file types other than .xlsx supported?
- I-Q6: Does Ctrl+Alt+R apply on all platforms?
```

### Doc 4: Keyboard shortcuts

```
Doc type: Reference
Audience: All Contoso Charts users

[S0] Version
- Available in Contoso Charts 4.3 and later. (R3, Done, 4.3)

[S1] New shortcut
- Ctrl+Alt+R: refreshes the selected chart (charts linked to an Excel workbook). (R3, Done, 4.3)

Already asked (don't repeat):
- I-Q6: Does Ctrl+Alt+R apply on all platforms?
- I-Q7: Does a keyboard shortcuts reference article exist, and what is its title?
```

## 4. Decision log

| Topic | Earlier decision (source) | Final decision (source) |
|---|---|---|
| Refresh mode | Auto-refresh every 5 minutes (R1, Oct 2) | Manual refresh only (R1, Oct 9) |
| Workbook open in Excel | Unknown whether the workbook must be closed (R2, Oct 10) | Refresh works while the workbook is open and reads the last saved version (R5, Oct 13) |
| Refresh in right-click menu | Proposed (R4) | Won't Fix (R4) |

## 5. Excluded

| Item | Source | Reason |
|---|---|---|
| Auto-refresh every 5 minutes | R1, Oct 2 | Not shipping (superseded) |
| Auto-refresh in a later version ("maybe") | R1, Oct 9 | Speculation |
| Google Sheets support ("might look at it next year") | R2, Oct 10 | Speculation |
| "Refresh" in the chart's right-click menu | R4 | Not shipping (Won't Fix) |
| Refresh timing from internal test on a large deck | R1, Oct 3 | Confidential (internal performance number) |
| Customer name requesting the feature | R1, Oct 4 | Confidential |
| Internal project code name | R1, Oct 9 | Confidential |
| Names of the PM, developer, and Support lead | R1, R2, R6 | Confidential |
| Ticket numbers and pull request number | R3, R4, R5 | Confidential |
| Customer complaints and Support's request for a fix | R6, Oct 14 | Internal (moved to Doc impact "Why") |

## 6. Questions for the PM or SME

- **I-Q1:** Which product versions does the corrected text in "Link a chart to Excel data" apply to? Should it cover only 4.3 and later, or all versions the article covers?
- **I-Q2:** Where is the Change Source command, and what are the steps to relink a chart to a moved or renamed workbook?
- **I-Q3:** What determines how many series slots a chart has? Can users add slots so the ignored rows appear?
- **I-Q4:** During Refresh All Charts, are charts with data-grid data skipped silently? What do Refresh Data and Ctrl+Alt+R do when no chart, or an unlinked chart, is selected (button disabled, message, nothing)?
- **I-Q5:** Is .xlsx the only supported format, or do .xlsm, .xls, or .csv workbooks also refresh?
- **I-Q6:** Does Ctrl+Alt+R apply on all supported platforms, or is there a different shortcut (for example, on Mac)?
- **I-Q7:** Does a keyboard shortcuts reference article exist, and what is its title?

## 7. Scope check

Please confirm the doc impact list before drafting starts.
