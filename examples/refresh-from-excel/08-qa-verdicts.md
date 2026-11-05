# Stage 5 output: Doc QA v1 — release verdicts

**Input:** the approved plan, link map, and Source pack 1, plus five drafts for the release:

- "Update linked chart data": the real draft from [04-draft-update-linked-chart-data.md](04-draft-update-linked-chart-data.md).
- "Charts don't update after editing Excel": the real draft from [06-draft-troubleshooting.md](06-draft-troubleshooting.md) with the reviewer's fixes applied, **plus two planted defects** (a link to intake's old title, and "Refresh All").
- "Error messages," "Keyboard shortcuts," and "What's new": **constructed** short updates with planted defects, to test cross-article checks.

The full QA input is `qa-inputs-data-refresh.md` in the portfolio, and the answer key is `qa-answer-key.md`.

**Agent:** Doc QA v1 (`qa-agent-v1.md`), with house-style.md v1.1
**Run:** Claude Projects, November 2026. Output copied verbatim; chat tables converted to Markdown.

---

## 1. Release summary

Five of the six planned drafts were submitted. "Link a chart to Excel data" (Update) is missing. Two articles use a title that doesn't exist for the main task article, and one draft states a file-format fact that contradicts the source pack. The two rewritten articles are blocked on open SME questions, and one Error messages entry gives a fix that has no source.

**Ready: 0 · Ready after fixes: 2 · Blocked: 3 · Missing: 1**

## 2. Doc status

| Draft | Brief compliance | Links | Terms | Facts | Open markers | Verdict |
|---|---|---|---|---|---|---|
| Update linked chart data | Title and type match plan. Heading order not checkable because Brief 1 isn't in the excerpt. | ✅ 5/5 | ✅ | ✅ | 4 GAPs (I-Q2, I-Q3, I-Q4, I-Q6) | Blocked |
| Charts don't update after editing Excel | Title and type match plan. Heading order not checkable because Brief 2 isn't in the excerpt. | Wrong title for Update linked chart data (QA-2) | "Refresh All" (QA-3) | ✅ | 1 GAP (I-Q2) | Blocked |
| Link a chart to Excel data | Missing (QA-1) | Not checkable | Not checkable | Not checkable | Not checkable | Missing |
| Error messages | ✅ Two entries added. Fit with existing table format not checkable from excerpt. | Missing link to Update linked chart data (QA-5) | Message text mismatch (QA-4) | Unsourced fix (QA-6) | 0 | Blocked |
| Keyboard shortcuts | ✅ | ✅ | "Ctrl + Alt + R" (QA-7) | ✅ | 0 | Ready after fixes |
| What's new in Contoso Charts | Heading isn't "Contoso Charts 4.3" (QA-8). Placement above 4.2 not checkable from excerpt. | Wrong title for Update linked chart data (QA-10) | "Version 4.3" (QA-8) | CSV claim contradicts S2 (QA-9) | 0 | Ready after fixes |

## 3. Issues

| QA-# | Draft | Check | Problem | Evidence (quote) | Fix | Needs SME? |
|---|---|---|---|---|---|---|
| QA-1 | Link a chart to Excel data | 1. Completeness | Plan row 3 (Update) has no draft. Brief 3 also isn't in the plan excerpt. | Plan: "\| 3 \| Link a chart to Excel data \| Update \| Task \| Work with data \|" | Submit the draft and Brief 3 for QA. The existing article still works as a link target. | No |
| QA-2 | Charts don't update after editing Excel | 3b, 3c. Links | Link text uses a title that isn't in the plan or the inventory. | "For more information, see Refresh a chart linked to Excel data." | Change to "Update linked chart data." | No |
| QA-3 | Charts don't update after editing Excel | 4. Terminology | Button name doesn't match S3 or the other drafts. | "To refresh every linked chart, select Refresh All." | Use Refresh All Charts. | No |
| QA-4 | Error messages | 7. Message text | Message is missing "the." | "Can't find linked workbook. Use Change Source to relink it." | Match S4 exactly: "Can't find the linked workbook. Use Change Source to relink it." | No |
| QA-5 | Error messages | 3a. Links | Link map requires a link to Update linked chart data, and neither new entry has one. | Fix columns contain only "see Fix a broken link to an Excel workbook" and "Delete the extra rows in Excel, or split the data into two charts." | Add a link to "Update linked chart data" where the brief intends it. | No |
| QA-6 | Error messages | 5, 6. Facts and unsourced facts | Fix has no source tag and isn't in the source pack. Update linked chart data leaves the same cell as an open GAP waiting on I-Q3, so the two drafts disagree. | "Delete the extra rows in Excel, or split the data into two charts." | Replace with a [GAP] tied to I-Q3 until the SME answers, then use the same wording in both drafts. | Yes (I-Q3) |
| QA-7 | Keyboard shortcuts | 4. Terminology | Shortcut format differs from S3 and the other drafts. | "Ctrl + Alt + R" | Use "Ctrl+Alt+R," unless existing rows in the article use the spaced format. Check against them. | No |
| QA-8 | What's new in Contoso Charts | 2, 4. Brief compliance and version format | Brief 6 asks for a "Contoso Charts 4.3" entry, and house-style rule 18 requires the product name. | "## Version 4.3" | Change heading to "Contoso Charts 4.3." | No |
| QA-9 | What's new in Contoso Charts | 5, 6. Facts and unsourced facts | CSV support contradicts S2, and the sentence has no source tag. Update linked chart data correctly states .xlsx only. | "Refresh works with Excel workbooks (.xlsx) and CSV files." | Remove "and CSV files" and tag [S2]. S2 is explicit: "Refresh works only for charts linked to an Excel workbook (.xlsx)." | No |
| QA-10 | What's new in Contoso Charts | 3b, 3c. Links | Link text uses a title that isn't in the plan or the inventory. | "For more information, see Refresh a chart linked to Excel data and Keyboard shortcuts." | Change to "Update linked chart data." | No |

## 4. Link check

| From | Link text | Expected destination | Status |
|---|---|---|---|
| Update linked chart data | Link a chart to Excel data | Link a chart to Excel data | OK |
| Update linked chart data | Fix a broken link to an Excel workbook | Fix a broken link to an Excel workbook | OK |
| Update linked chart data | Change a chart's data source | Change a chart's data source | OK |
| Update linked chart data | Error messages | Error messages | OK |
| Update linked chart data | Keyboard shortcuts | Keyboard shortcuts | OK |
| Charts don't update after editing Excel | Refresh a chart linked to Excel data | Update linked chart data | Wrong title |
| Charts don't update after editing Excel | Link a chart to Excel data | Link a chart to Excel data | OK |
| Charts don't update after editing Excel | Fix a broken link to an Excel workbook | Fix a broken link to an Excel workbook | OK |
| Error messages | Fix a broken link to an Excel workbook | Fix a broken link to an Excel workbook | OK |
| Error messages | (none) | Update linked chart data | Missing |
| Keyboard shortcuts | Update linked chart data | Update linked chart data | OK |
| What's new in Contoso Charts | Refresh a chart linked to Excel data | Update linked chart data | Wrong title |
| What's new in Contoso Charts | Keyboard shortcuts | Keyboard shortcuts | OK |

None of the drafts link to anything outside the plan.

## 5. Terminology table

| Term | Variants found (draft) | Correct form | Source |
|---|---|---|---|
| Refresh-all button | Refresh All Charts (Update linked chart data, What's new); Refresh All (Charts don't update) | Refresh All Charts | S3 |
| Refresh-selected button | Refresh Data (Update linked chart data, Charts don't update, What's new) | Refresh Data ✅ | S3 |
| Refresh shortcut | Ctrl+Alt+R (Update linked chart data, What's new); Ctrl + Alt + R (Keyboard shortcuts) | Ctrl+Alt+R | S3 |
| Product and version | Contoso Charts 4.3 (Update linked chart data, Keyboard shortcuts); Version 4.3 (What's new) | Contoso Charts 4.3 | S0, Brief 6, rule 18 |
| Task article title | Update linked chart data (Update linked chart data, Keyboard shortcuts); Refresh a chart linked to Excel data (Charts don't update, What's new) | Update linked chart data | Doc plan row 1 |
| Workbook-not-found message | "Can't find the linked workbook. Use Change Source to relink it." (Update linked chart data, Charts don't update); "Can't find linked workbook. Use Change Source to relink it." (Error messages) | "Can't find the linked workbook. Use Change Source to relink it." | S4 |
| Change Source | Change Source (Update linked chart data, Charts don't update) | Change Source ✅ | S4 |
| Tab and group | Contoso Charts tab, Data group (Update linked chart data, Charts don't update) | ✅ | S3 |

## 6. Questions blocking release

| Question | Waits on | Blocks |
|---|---|---|
| I-Q2 | Steps for using Change Source to relink a chart | Update linked chart data; Charts don't update after editing Excel |
| I-Q3 | Series slots: how many there are and what the reader should do when the chart is full | Update linked chart data; Error messages (QA-6) |
| I-Q4 | What Refresh All Charts does to charts that aren't linked | Update linked chart data |
| I-Q6 | Mac equivalent of Ctrl+Alt+R | Update linked chart data. If a Mac shortcut exists, Keyboard shortcuts and What's new in Contoso Charts will also need it. |
| QA-Q1 (new) | Where are the draft and Brief 3 for "Link a chart to Excel data"? Briefs 1 and 2 are also needed to confirm the heading order of the two rewrites. | Release completeness; brief compliance for Update linked chart data and Charts don't update after editing Excel |

## 7. Sign-off

Please review the release verdicts before publishing.

---

**Scored against the answer key:** all 10 planted defects found, no false alarms, plus **QA-5**, a missing link that wasn't planted.
