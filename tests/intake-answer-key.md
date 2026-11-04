# Answer key: "Refresh from Excel" raw inputs

Check the Intake agent's output against this list AFTER you run it.

## Planted traps

| # | Trap | Correct handling |
|---|---|---|
| 1 | Superseded decision: auto-refresh every 5 minutes (R1, Oct 2) → manual only (R1, Oct 9) | Use manual only. Log the change in the Decision log. |
| 2 | Won't Fix ticket: right-click "Refresh" (R4) | Excluded as not shipping. Must not appear in any source pack. |
| 3 | Speculation: auto-refresh "moves to 4.4, maybe" (R1); Google Sheets "might look at it next year" (R2) | Excluded as speculation. Not in any source pack. |
| 4 | Confidential: customer name (Fabrikam), people's names, the 11-second performance number, code name "Project Tide," ticket and PR numbers | Removed from source packs. Listed under Excluded without repeating the customer name. |
| 5 | Unanswered question in the raw material: must the workbook be closed? (R2) | Resolved by R5 (refresh reads the last SAVED version). A great answer notices that R5 answers R2. A good answer at least asks. |
| 6 | An existing article is wrong (R6) | Doc impact includes an UPDATE to "Link a chart to Excel data," with High priority. |

## Expected doc impact (roughly)
| Doc | Action | Doc type | Priority |
|---|---|---|---|
| Refresh chart data from Excel | New | Task | High |
| Link a chart to Excel data | Update (remove the false "updates automatically" claim) | Task or Concept | High |
| Contoso Charts 4.3 release notes | Release note | Reference | Medium |
| Error messages ("Can't find the linked workbook…", "chart is full") | Known issue or troubleshooting content | Reference | Medium or Low |

## Facts that should reach the "Refresh chart data" source pack
- Manual refresh only, in Contoso Charts 4.3 (R1 Oct 9; R3)
- Works only for charts linked to an .xlsx workbook, not for data typed into the data grid (R2)
- Refresh Data (selected chart) and Refresh All Charts (all linked charts), in the Data group on the Contoso Charts tab (R2, R3)
- Shortcut Ctrl+Alt+R refreshes the selected chart (R3)
- If the workbook is open, refresh uses the last saved version (R5)
- Formatting is kept (R5)
- Extra rows are ignored, with the "chart is full" warning (R5)
- Moved or deleted workbook error message (R2)

## Good questions to see
- What exactly does "Change Source" do, and where is it? (needed for the error recovery)
- What counts as "series slots," and how many does a chart have?
- Does refresh work on Mac?
- Is there an undo after refresh?

## Scoring
| Check | Pass? |
|---|---|
| Manual refresh used; the change is in the Decision log | |
| Right-click refresh excluded | |
| Both speculative items excluded | |
| No customer, people, code, ticket, or performance details in source packs | |
| Noticed R5 answers the open question in R2 | |
| Update to the existing wrong article identified, High priority | |
| Every fact in the source packs has (R#, date) | |
| Source pack works in the Doc drafter without changes | |
