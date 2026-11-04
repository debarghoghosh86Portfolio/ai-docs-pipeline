# Answer key: QA for the "Refresh from Excel" release

Check the QA agent's output against this list AFTER you run it.

## Planted defects

| # | Draft | Defect | Check | Expected verdict impact |
|---|---|---|---|---|
| 1 | (missing) | No draft for "Link a chart to Excel data" (planned Update, High priority) | Completeness | Missing |
| 2 | Charts don't update… | "Refresh All" instead of the exact label "Refresh All Charts" | Terminology | Fix |
| 3 | Charts don't update… | Links to "Refresh a chart linked to Excel data", intake's old title. The final title is "Update linked chart data" | Links | Fix |
| 4 | What's new | Same wrong link title as #3 | Links | Fix |
| 5 | What's new | "Refresh works with Excel workbooks (.xlsx) and CSV files" contradicts [S2] (.xlsx only), and "CSV" has no source tag | Facts / Unsourced | Needs SME or remove; Blocked or fix |
| 6 | What's new | Heading "Version 4.3" doesn't name the product (house-style rule 18). Other drafts say "Contoso Charts 4.3" | Terminology | Fix |
| 7 | Error messages | Message text "Can't find linked workbook…" is missing "the"; doesn't match [S4] or the other drafts | Message text | Fix |
| 8 | Error messages | Fix "Delete the extra rows in Excel, or split the data into two charts" has no source; it's invented | Unsourced | Needs SME (ties to I-Q3) |
| 9 | Keyboard shortcuts | "Ctrl + Alt + R" with spaces; other drafts use "Ctrl+Alt+R" | Terminology | Fix |
| 10 | Update linked chart data / Charts don't update… | Open GAPs: I-Q6, I-Q4, I-Q2, I-Q3 (A); I-Q2 (B) | Open markers | Blocked |

## Things that are correct (no false alarms)

- "Update linked chart data" has all five links from the link map.
- "Charts don't update after editing Excel" links to "Link a chart to Excel data" and "Fix a broken link to an Excel workbook" correctly.
- "Fix a broken link to an Excel workbook" and "Change a chart's data source" are valid link targets (existing, unchanged articles).
- "Charts need a manual refresh" is a cause heading. That's correct under house-style v1.1, not a QA issue.
- The reviewer already passed these drafts for sentence-level style. QA shouldn't re-flag style issues.

## Expected verdicts (roughly)

| Draft | Verdict |
|---|---|
| Update linked chart data | Blocked (4 open GAPs) |
| Charts don't update after editing Excel | Blocked (1 open GAP) + fixes (#2, #3) |
| Error messages | Blocked or Ready after fixes (#7 fix; #8 needs SME) |
| Keyboard shortcuts | Ready after fixes (#9) |
| What's new in Contoso Charts | Blocked or Ready after fixes (#4, #6; #5 needs SME or removal) |
| Link a chart to Excel data | Missing |

## Scoring

| Check | Pass? |
|---|---|
| Missing draft found | |
| Both wrong link titles found | |
| "Refresh All" label found | |
| CSV contradiction found | |
| Invented fix in Error messages found | |
| Message text mismatch found | |
| "Version 4.3" without product name found | |
| "Ctrl + Alt + R" spacing found | |
| Open GAPs counted, with their question numbers | |
| No false alarms from the "correct" list | |
