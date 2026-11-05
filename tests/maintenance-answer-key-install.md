# Answer key: maintenance after the Installation and Getting started release

Written BEFORE running Doc maintenance v2 on `maintenance-inputs-install.md`.

## Expected change sets

| # | Change | Articles that must be covered | Status |
|---|---|---|---|
| 1 | Color Palette → Colors (C2) | Contoso Charts overview (tab table). The sweep should also check the guide's ribbon figure. | Hold until 4.4.1 ships |
| 2 | Windows 10 dropped (C2) | System requirements, plus Install (the Windows 10 uninstall path). Keep a version note for 4.4 users, and don't delete it. | Hold until 4.4.1 ships |
| 3 | I-Q5 answered: charts become static pictures, and links are removed (C1) | Install > Uninstall (and possibly Link a chart to Excel data) | Ready |
| 4 | Support signal: no Welcome pane after an update (C4) | Contoso Charts overview, Create a chart, and Install > Update | **Blocked: needs SME confirmation.** It's a support finding, not a spec. Ask a question, and don't state it as fact. |

## No doc impact (traps)

| C# | Why |
|---|---|
| C3 | Reverted, and not in any build. (It would also bring back the old "Insert Chart" name.) |
| C5 | Speculation ("Maybe … 4.6") |
| C6 | Internal refactor |
| C2, the hidden sheets fix | A bug fix with no doc text affected. A known-issue note at most; it isn't required. |

## Scoring

| Check | Pass? |
|---|---|
| Rename sweep finds the overview table (and mentions the figure) | |
| Windows 10 change keeps a 4.4 version note and covers the uninstall path | |
| The I-Q5 answer routed to Install > Uninstall (no GAP existed, so it adds new content) | |
| Support signal raised as a question, not a fact | |
| C3, C5, and C6 under No doc impact | |
| Hold until 4.4.1 for the C2 items | |
