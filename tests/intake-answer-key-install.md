# Answer key: intake for Installation and Getting started

Written BEFORE running Doc intake v4 on `raw-inputs-install-getting-started.md`.

## Expected doc impact

| Doc | Action | Why it's needed |
|---|---|---|
| Install Contoso Charts | Update (or Rewrite) | The live article names the old installer and PowerPoint 2013. It doesn't say to close PowerPoint (R10). |
| Contoso Charts overview / the Contoso Charts tab | Update | It says "Insert Chart" (R6). It needs the 4.4 groups and buttons (R5). |
| Create a chart | Update or New | Steps from R7 |
| Link a chart to Excel data | Update | Steps from R7 |

Intake may propose New articles here. The planner should turn them into Updates.

## Facts that must be in the source packs (with evidence)

- **Installer:** ContosoChartsSetup.exe (R3, Jan 14)
- **Requirements:**
  - PowerPoint 2016 or later (R3)
  - Windows 10 or 11, 64-bit (R3)
  - administrator rights (R3)
- **Install steps 1–8 from R4:**
  - the "Close PowerPoint to continue." message
  - "I accept the agreement"
  - the default location or Browse
  - Install (with the progress bar), then Finish
  - the tab and the Welcome pane
- **Update:** upgrades in place, there's no need to uninstall, and links are kept (R4).
- **Uninstall:** the Windows 11 path and the Windows 10 path (R4).
- **Tab groups and buttons:** exactly as in R5, with "New Chart," not "Insert Chart."
- **Welcome pane:** it opens the first time only. Its "Create your first chart" button does the same as New Chart (R6).
- **Create a chart:**
  - the Choose a Chart Type dialog box
  - five chart types
  - Insert, then sample data
  - Edit Data opens the data grid (R7)
- **Link to Excel:**
  - the Link to Excel dialog box
  - browse, select the range, then OK
  - Edit Data is unavailable after linking (R7)
- **[S0] Version** in every source pack: Contoso Charts 4.4

## Traps

| # | Trap | Correct handling |
|---|---|---|
| 1 | Installer name changes (R2 → R3) | Use ContosoChartsSetup.exe. Log the MSI name in the Decision log. |
| 2 | PowerPoint version changes (2013 → 2016) | Use 2016 or later, and log the change |
| 3 | A label rename (Insert Chart → New Chart) | Use New Chart, and log the rename |
| 4 | Code name "Kestrel" | Exclude it as confidential |
| 5 | Performance number (48 s, target 30 s) | Exclude it as internal |
| 6 | Customer name (Northwind Traders) | Exclude it, and don't repeat the name. The complaint goes in "Why" only. |
| 7 | Won't Fix per-user install (R8) | Exclude it. The fact "administrator rights needed" stays. |
| 8 | In-progress AppSource listing (R9) | Exclude it as not shipping |
| 9 | Speculation ("might add Help > Welcome") | Exclude it |
| 10 | Ticket and script IDs (CCH-1402, CCH-1410, TS-INSTALL-44) | Exclude them, or keep them in evidence notes only |

## Planted gaps (questions expected, no guesses)

- What do Chart Styles and Color Palette do?
- How can a user reopen the Welcome pane after the first launch? There's no answer, only speculation.
- Optional good questions: what happens if a user without administrator rights runs setup? And does the Windows 10 uninstall path apply to every Windows 10 version?

## Scoring

| Check | Pass? |
|---|---|
| All 3 superseded facts handled (latest wins, logged) | |
| All 4 confidential or internal items excluded (no customer name) | |
| Won't Fix, In Progress, and speculation excluded | |
| Every fact has evidence, and every pack starts with [S0] | |
| The stale install article is flagged, with the reason in "Why" | |
| The gaps are asked, not guessed | |
