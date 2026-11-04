[R1] Slack thread — #contoso-charts-dev — Oct 2–9

Oct 2, Arjun (PM): Kicking off "Refresh from Excel" for 4.3. Charts linked to
an Excel workbook will update with the new data. Plan is auto-refresh every
5 minutes.
Oct 3, Mei (dev): Auto-refresh every 5 min is going to hurt perf on big decks.
In my test, a 40-chart deck took 11 seconds per refresh.
Oct 4, Arjun (PM): Ugh. Fabrikam is the customer pushing for this, they'll
want auto. Let's think about it.
Oct 9, Arjun (PM): Decision: 4.3 ships MANUAL refresh only. Auto-refresh moves
to 4.4, maybe. Internally we're calling this "Project Tide."

[R2] Meeting notes — Docs/PM sync — Oct 10

- Refresh works only for charts linked to an Excel workbook (.xlsx). Charts
  with data typed into the Contoso Charts data grid can't be refreshed.
- Two ways to refresh: "Refresh Data" button in the Data group on the Contoso
  Charts tab (refreshes the selected chart), and "Refresh All Charts" in the
  same group (refreshes every linked chart in the presentation).
- If the linked workbook has moved or been deleted, the user sees:
  "Can't find the linked workbook. Use Change Source to relink it."
- Someone asked about Google Sheets support. Arjun: "We might look at it
  next year."
- Requires the linked workbook to be closed in Excel? Mei wasn't sure.

[R3] Jira CCH-1301 — "Refresh Data button" — Status: Done — Fix version 4.3
Adds Refresh Data and Refresh All Charts buttons to the Data group.
Keyboard shortcut: Ctrl+Alt+R refreshes the selected chart.

[R4] Jira CCH-1307 — "Refresh from right-click menu" — Status: Won't Fix
Add "Refresh" to the chart's right-click menu. Closed: out of scope for 4.3.

[R5] Pull request #882 description — merged Oct 13

Implements manual refresh. If the workbook is open in Excel, refresh reads
the last SAVED version, not unsaved changes. Chart formatting (colors, fonts,
titles) is kept after refresh. If the new data has more rows than the chart
has series slots, extra rows are ignored and a warning appears:
"Some data wasn't added because the chart is full."

[R6] Email from Support lead — Oct 14

Heads-up: customers already ask why charts don't update when they change
Excel. The existing article "Link a chart to Excel data" says "Your chart
updates automatically when the Excel data changes." That was never true. We
need that fixed when 4.3 ships.
