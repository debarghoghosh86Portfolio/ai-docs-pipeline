# Answer key: maintenance after the 4.3 release

Check the Maintenance agent's output against this list AFTER you run it.

## Expected tickets

| # | Change | Severity | Articles that must be covered | Notes |
|---|---|---|---|---|
| 1 | Shortcut Ctrl+Alt+R → Ctrl+Shift+R (C1) | Critical | Update linked chart data; Keyboard shortcuts | Add a version note (4.4 and later vs. 4.3). Do NOT change the 4.3 entry in What's new (trap). |
| 2 | Change Source → Change Data Source, and new message text (C2) | Critical | Update linked chart data; Charts don't update after editing Excel; Error messages; Change a chart's data source; Fix a broken link to an Excel workbook | The sweep must find all five. "Fix a broken link" (2023) is the easiest to miss. |
| 3 | Export limit 20 → 50 (C1) | High | Export charts to PDF | Reuse the old feature: not a refresh article. |
| 4 | Refresh All Charts skips unlinked charts and shows a summary (C1) | Medium | Update linked chart data (fills the I-Q4 GAP); Charts don't update after editing Excel (optional) | It answers I-Q4 and adds a result for the step. |
| 5 | I-Q3 answered: 20 series slots; split the data or remove rows (C3) | Medium | Update linked chart data; Error messages | Fills two GAPs. |
| 6 | I-Q6 answered: refresh is Windows only (C3) | Medium (or High) | Update linked chart data; Keyboard shortcuts | Add a prerequisite / platform note. |
| 7 | I-Q2 answered: existing steps are correct (C3) | Medium | Update linked chart data (GAP → link) | Combine with ticket 2's rename. |
| 8 | 14 support tickets: Refresh Data grayed out (C4) | Low or Medium | Update linked chart data; Charts don't update after editing Excel | Clarity: say the button is unavailable when no chart is selected or the chart uses data-grid data. |
| 9 | New 4.4 entry needed in What's new (C1, C2) | Medium | What's new in Contoso Charts | New entry, not an edit to 4.3. |

## No doc impact (traps)

| C# | Why |
|---|---|
| C5 | Internal refactor, no visible change |
| C6 | Speculation ("maybe," 4.5) |
| C7 | Won't Fix |

## Good extras to see

- Notices that the shortcut change and the platform answer both affect the
  Keyboard shortcuts row, and combines them.
- Notices "Fix a broken link to an Excel workbook" is from 2023 and overlaps
  "Change a chart's data source" (the planner flagged this before) and
  suggests routing that to the Planner.
- Asks whether 4.3 users still need the Ctrl+Alt+R information.
- Routes the multi-article rename (ticket 2) to Intake or Planner, not straight
  to the Drafter.

## Scoring

| Check | Pass? |
|---|---|
| Shortcut change: both articles, Critical, version note | |
| What's new 4.3 entry left unchanged | |
| Rename sweep: all five articles found | |
| Export limit change found (non-refresh article) | |
| I-Q4, I-Q3, I-Q6, I-Q2 answers matched to their GAPs | |
| Support tickets turned into a clarity ticket | |
| New 4.4 release notes entry | |
| C5, C6, C7 under No doc impact | |
| Tickets ordered by severity | |
| Sensible routing (multi-article → Intake/Planner; small fixes → Drafter) | |
