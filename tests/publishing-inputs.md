=== PART 1: RELEASE INFO ===
Release: Contoso Charts 4.3 docs
Release date: 2026-11-20
Repository: contoso-charts-docs (Markdown, one file per article)

Front matter schema:
---
title: ""
description: ""
slug: ""
doc_type: ""          # task | troubleshooting | reference | concept
toc_section: ""
product_version: ""   # for example "4.3+"
last_updated: ""      # YYYY-MM-DD
keywords: []
---


=== PART 2: SLUG MAP (articles on the live site) ===
| Title | Slug |
| Update linked chart data | /work-with-data/update-linked-chart-data |
| Link a chart to Excel data | /work-with-data/link-chart-to-excel |
| Change a chart's data source | /work-with-data/change-data-source |
| Charts don't update after editing Excel | /troubleshooting/charts-dont-update |
| Fix a broken link to an Excel workbook | /troubleshooting/fix-broken-link |
| Error messages | /reference/error-messages |
| Keyboard shortcuts | /reference/keyboard-shortcuts |
| What's new in Contoso Charts | /getting-started/whats-new |


=== PART 3: APPROVED DOC PLAN (excerpt) ===
| # | Title | Action | Doc type | TOC section |
| 1 | Update linked chart data | Rewrite | Task | Work with data |
| 2 | Charts don't update after editing Excel | Rewrite | Troubleshooting | Troubleshooting |
| 3 | Link a chart to Excel data | Update | Task | Work with data |
| 4 | Error messages | Update | Reference | Reference |
| 5 | Keyboard shortcuts | Update | Reference | Reference |
| 6 | What's new in Contoso Charts | Update | Reference | Getting started |
No articles are retired or renamed in this release.


=== PART 4: QA REPORT (final round, after writer fixes) ===
| Draft | QA verdict | Fixes the writer says were applied |
| Update linked chart data | Ready | — (SME answered I-Q2, I-Q3, I-Q4, I-Q6; GAPs filled and re-reviewed) |
| Charts don't update after editing Excel | Ready after fixes | QA-2 (link title), QA-3 ("Refresh All" → "Refresh All Charts") |
| Link a chart to Excel data | Missing | — |
| Error messages | Blocked | QA-6 still waiting on the SME |
| Keyboard shortcuts | Ready after fixes | QA-7 ("Ctrl + Alt + R" → "Ctrl+Alt+R") |
| What's new in Contoso Charts | Ready after fixes | QA-8 (heading "Contoso Charts 4.3"), QA-9 (removed "and CSV files"), QA-10 (link title) |


=== PART 5: MAINTENANCE CHANGE SETS ===
| CS-# | Change | Status | Drafted text provided? |
| CS-2 | Refresh shortcut becomes Ctrl+Shift+R (4.4) | Hold until release | No |
| CS-3 | Refresh is Windows only | Ready | No |


=== PART 6: FINAL DRAFTS ===

--- DRAFT: Update linked chart data (Rewrite) ---

# Update linked chart data

Refresh a linked chart to update it with the current data from its Excel workbook. [S1] Refresh is manual, so charts don't update automatically when the Excel data changes. [S1] Refresh keeps the chart's formatting, such as colors, fonts, and titles. [S1]

## Before you begin

- You need Contoso Charts 4.3 or later on Windows. Refresh isn't available on Mac. [S0] [S2]
- The chart must be linked to an Excel workbook (.xlsx). [S2] For more information, see Link a chart to Excel data.
- If the workbook is open in Excel, save it before you refresh. Refresh reads the last saved version and doesn't include unsaved changes. [S2]

## Refresh the selected chart

1. Select the chart. [S3]
2. On the **Contoso Charts** tab, in the **Data** group, select **Refresh Data**. The chart updates with the current data from its workbook. [S3] [S1]

You can also select the chart and press Ctrl+Alt+R. [S3] For more information, see Keyboard shortcuts.

## Refresh all linked charts in a presentation

- On the **Contoso Charts** tab, in the **Data** group, select **Refresh All Charts**. Every linked chart in the presentation refreshes. Charts that aren't linked to a workbook stay as they are. [S3] (R3, Done, 4.3)

## Messages you might see

| Message | Cause | What to do |
|---|---|---|
| "Can't find the linked workbook. Use Change Source to relink it." | Someone moved or deleted the linked workbook. [S4] | Relink the chart by using **Change Source**. For more information, see Change a chart's data source. |
| "Some data wasn't added because the chart is full." | The workbook has more rows than the chart has series slots. Each chart has 20 series slots. [S4] | Split the data across two charts, or remove rows. |

For more information, see Error messages.

--- DRAFT: Charts don't update after editing Excel (Rewrite) ---

# Charts don't update after editing Excel

This article helps you fix a linked chart that still shows old data after you edit its Excel workbook.

## Charts need a manual refresh

Refresh is manual. Charts don't update automatically when the Excel data changes. [S1]

1. Select the chart you want to update. [S3]
2. On the **Contoso Charts** tab, in the **Data** group, select **Refresh Data**. The chart updates with the current data from its Excel workbook. [S3] [S1]

To refresh every linked chart, select **Refresh All**. [S3] For more information, see Update linked chart data.

## The workbook has unsaved changes

Refresh reads the last saved version of the workbook and doesn't include unsaved changes. [S2]

1. In Excel, save the workbook. [S2]
2. In the presentation, select the chart, and then select **Refresh Data**. The chart updates with the saved data. [S3] [S1]

## Someone moved or deleted the workbook

If someone moved or deleted the linked workbook, you see this message: "Can't find the linked workbook. Use Change Source to relink it." [S4] For more information, see Fix a broken link to an Excel workbook.

--- DRAFT: Keyboard shortcuts (Update: new row only) ---

Add this row under "Contoso Charts tab":

| Shortcut | Action |
|---|---|
| Ctrl+Alt+R | Refresh the selected chart's data from Excel (Contoso Charts 4.3 and later). Mac shortcut TBD (I-Q6). For more information, see Update linked chart data. |

--- DRAFT: What's new in Contoso Charts (Update: new 4.3 entry, above 4.2) ---

## Contoso Charts 4.3

You can now refresh linked charts with the latest data from Excel. Use **Refresh Data** to refresh the selected chart, **Refresh All Charts** to refresh every linked chart, or press Ctrl+Alt+R. [S3] (R3, Done, 4.3) Refresh works with Excel workbooks (.xlsx). Charts don't update automatically. [S1] [S2]

For more information, see Update linked chart data and Keyboard shortcuts.
