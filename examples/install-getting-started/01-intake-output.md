# Stage 1 output: Doc intake v4, Installation and Getting started

**Input:** `raw-inputs-install-getting-started.md` (constructed test material with planted traps). The answer key is `intake-answer-key-install.md`.
**Agent:** Doc intake v4 (`intake-agent-v4.md`)
**Run:** Claude Projects, November 2026. The output is copied verbatim, with chat tables converted to Markdown.

---

## 1. Change summary

Kind: Doc request

The docs lead asked for source packs for two chapters of the Contoso Charts 4.4 User Guide. Installation covers requirements, installing, updating, and uninstalling. Getting started covers the Contoso Charts tab, creating a chart, linking it to Excel, and a first refresh and export. Version 4.4 changes installation: there is a new single-file installer, PowerPoint 2016 or later is required, 64-bit Windows is required, and administrator rights are required. The existing install article is out of date. The sources cover creating and linking a chart well. No source has a procedure for refreshing or exporting a chart. This affects anyone installing or starting to use Contoso Charts 4.4, including IT administrators who deploy it.

## 2. Doc impact

| # | Doc | Action | Doc type | Audience | Priority | Why |
|---|---|---|---|---|---|---|
| 1 | Installation: System requirements | Update | Reference | PowerPoint users, IT administrators | High | The existing install article still says PowerPoint 2013 works. Requirements changed in 4.4. A support request reported this. |
| 2 | Installation: Install, update, and uninstall Contoso Charts | Update | Task | PowerPoint users, IT administrators | High | The existing article doesn't say to close PowerPoint. Users who installed with PowerPoint open couldn't find the tab. The installer file changed in 4.4. |
| 3 | Getting started: The Contoso Charts tab and Welcome pane | New | Reference | PowerPoint users new to Contoso Charts | Medium | Requested by the docs lead. Users need to know where the commands are. A button was renamed (Insert Chart is now New Chart). |
| 4 | Getting started: Create a chart and link it to Excel | New | Task | PowerPoint users new to Contoso Charts | High | Requested by the docs lead. This is the core first task. |
| 5 | Getting started: First refresh and export | Needs source | Task | PowerPoint users new to Contoso Charts | High | Requested by the docs lead. No raw source describes the refresh or export procedure. See I-Q7 and I-Q8. |

## 3. Source packs

### Pack 1: Installation: System requirements

```
Doc type: Reference
Audience: PowerPoint users, IT administrators

[S0] Version
- Available in Contoso Charts 4.4 and later. (R3, Jan 14)

[S1] Requirements
- Windows 10 or Windows 11, 64-bit. (R3, Jan 14)
- PowerPoint 2016 or later. (R3, Jan 14)
- Contoso Charts 4.4 doesn't support PowerPoint 2013. (R3, Jan 14)
- Installing requires administrator rights on the computer. (R3, Jan 14)

[S2] Installer file
- The installer is a single file: ContosoChartsSetup.exe. (R3, Jan 14)
- No MSI package is available for 4.4. (R3, Jan 14)

[S3] Corrections to the current article
- The current install article says PowerPoint 2013 works. This is incorrect for 4.4. (R10, Jan 15; R3, Jan 14)

Already asked (don't repeat):
- I-Q1 — Where users get ContosoChartsSetup.exe
- I-Q2 — What happens if a user without administrator rights runs setup
- I-Q4 — Whether the chapter keeps any content for 4.3 or earlier
```

### Pack 2: Installation: Install, update, and uninstall Contoso Charts

```
Doc type: Task
Audience: PowerPoint users, IT administrators

[S0] Version
- Available in Contoso Charts 4.4 and later. (R4, Passed, build 4.4)

[S1] Before you install
- You need administrator rights on the computer. (R3, Jan 14)
- Close PowerPoint before you run setup. If PowerPoint is open, setup shows "Close PowerPoint to continue." and waits. (R4, Passed, build 4.4)

[S2] Install steps (in order, with results)
1. Close PowerPoint. (R4, Passed, build 4.4)
2. Double-click ContosoChartsSetup.exe. (R4, Passed, build 4.4)
3. On the Welcome page, select Next. (R4, Passed, build 4.4)
4. Read the license agreement, select "I accept the agreement," then select Next. (R4, Passed, build 4.4)
5. Keep the default install location, or select Browse to choose another folder. Select Next. (R4, Passed, build 4.4)
6. Select Install. A progress bar shows the installation status. (R4, Passed, build 4.4)
7. Select Finish. (R4, Passed, build 4.4)
8. Open PowerPoint. The Contoso Charts tab appears on the ribbon. The first time, the Welcome pane opens on the right. (R4, Passed, build 4.4)

[S3] Update from 4.3
- To update, run the 4.4 setup file. It upgrades in place. (R4, Passed, build 4.4)
- You don't need to uninstall 4.3 first. (R4, Passed, build 4.4)
- Existing linked charts keep their links after the update. (R4, Passed, build 4.4)

[S4] Uninstall
- Windows 11: Settings > Apps > Installed apps > Contoso Charts > More (...) > Uninstall. (R4, Passed, build 4.4)
- Windows 10: Control Panel > Programs > Programs and Features > Contoso Charts > Uninstall. (R4, Passed, build 4.4)

[S5] Corrections to the current article
- The current install article doesn't say to close PowerPoint before setup. Add this step. (R10, Jan 15; R4, Passed, build 4.4)
- The current install article says PowerPoint 2013 works. This is incorrect for 4.4. (R10, Jan 15; R3, Jan 14)

Already asked (don't repeat):
- I-Q1 — Where users get ContosoChartsSetup.exe
- I-Q2 — What happens if a user without administrator rights runs setup
- I-Q3 — Whether updating requires closing PowerPoint, and whether versions earlier than 4.3 can update in place
- I-Q4 — Whether the chapter keeps any content for 4.3 or earlier
- I-Q5 — What happens to linked charts in existing presentations after uninstall
```

### Pack 3: Getting started: The Contoso Charts tab and Welcome pane

```
Doc type: Reference
Audience: PowerPoint users new to Contoso Charts

[S0] Version
- Available in Contoso Charts 4.4 and later. (R5, Jan 9, confirmed in build 4.4)

[S1] Contoso Charts tab: groups and buttons
- Create group: New Chart, Edit Data. Edit Data opens the data grid. (R5, Jan 9, confirmed in build 4.4)
- Data group: Link to Excel, Refresh Data, Refresh All Charts, Change Data Source. (R5, Jan 9, confirmed in build 4.4)
- Format group: Chart Styles, Color Palette. (R5, Jan 9, confirmed in build 4.4)
- Export group: Export to PDF. (R5, Jan 9, confirmed in build 4.4)
- The button for creating a chart is named New Chart. (R6, Jan 16)

[S2] Welcome pane
- The first time you open PowerPoint after installing, the Welcome pane opens on the right. (R4, Passed, build 4.4)
- The Welcome pane opens only the first time. (R6, Jan 16)
- The Welcome pane's "Create your first chart" button does the same thing as New Chart. (R6, Jan 16)

Already asked (don't repeat):
- I-Q6 — Whether users can reopen the Welcome pane in 4.4
- I-Q10 — Whether the overview article that says "Insert Chart" is in scope
```

### Pack 4: Getting started: Create a chart and link it to Excel

```
Doc type: Task
Audience: PowerPoint users new to Contoso Charts

[S0] Version
- Available in Contoso Charts 4.4 and later. (R7, Approved, shipped in 4.4)

[S1] Create a chart
- On the Contoso Charts tab, in the Create group, select New Chart. The "Choose a Chart Type" dialog box opens. (R7, Approved, shipped in 4.4)
- Chart types: Column, Bar, Line, Pie, Area. (R7, Approved, shipped in 4.4)
- Select a chart type, then select Insert. The chart appears on the slide with sample data. (R7, Approved, shipped in 4.4)
- The first time, you can also select "Create your first chart" in the Welcome pane. It does the same thing as New Chart. (R6, Jan 16)

[S2] Change data in a chart that isn't linked
- Select the chart, then select Edit Data. The data grid opens. (R7, Approved, shipped in 4.4)

[S3] Link a chart to Excel
- Select the chart. On the Contoso Charts tab, in the Data group, select Link to Excel. The "Link to Excel" dialog box opens. (R7, Approved, shipped in 4.4)
- Browse to the workbook (.xlsx), select the range, then select OK. The chart shows the data from that range. (R7, Approved, shipped in 4.4)

[S4] After linking
- After you link a chart, Edit Data is unavailable for that chart. Change the data in Excel instead, then refresh. (R7, Approved, shipped in 4.4)

Already asked (don't repeat):
- I-Q7 — Refresh procedure and behavior
- I-Q9 — Supported workbook formats and how users select the range
```

## 4. Decision log

| Topic | Earlier decision (source) | Final decision (source) |
|---|---|---|
| Installer file | ContosoCharts-Installer.msi (R2, Sep 3, 2025) | Single file ContosoChartsSetup.exe. No MSI package in 4.4. (R3, Jan 14) |
| Minimum PowerPoint version | PowerPoint 2013 or later (R2, Sep 3, 2025) | PowerPoint 2016 or later. PowerPoint 2013 isn't supported in 4.4. (R3, Jan 14) |
| Windows requirement | Windows 10 or Windows 11 (R2, Sep 3, 2025) | Windows 10 or Windows 11, 64-bit (R3, Jan 14) |
| Create button label | Insert Chart (old name, per R6, Jan 16) | New Chart (R5, Jan 9, confirmed in build 4.4; R6, Jan 16) |

## 5. Excluded

| Item | Source | Reason |
|---|---|---|
| Per-user install without administrator rights | R8 | Not shipping (Won't Fix) |
| Publishing Contoso Charts on AppSource | R9 | Not shipping (In Progress, targeted for a later release) |
| A Help > Welcome menu item to reopen the Welcome pane | R6, Jan 16 | Speculation ("might … later") |
| Installer code name | R3 | Confidential (code name) |
| Install time measured on test VM and its target | R4 | Confidential (internal performance numbers) |
| Customer name of the support email's sender | R10 | Confidential (customer name) |
| Ticket and test script IDs | R4, R8, R9 | Confidential (ticket numbers) |
| Support complaint about the missing tab and outdated article | R10 | Internal (reason for the doc; used only in Doc impact "Why") |
| Other chapters (What's new, Refresh charts, Data sources, Troubleshooting, Reference) | R1 | Out of scope for this request |

## 6. Questions for the PM or SME

- **I-Q1:** Where do users get ContosoChartsSetup.exe (download page, IT distribution, other)? No source says.
- **I-Q2:** What happens if a user without administrator rights runs setup? Is there an exact message to document?
- **I-Q3:** Does updating from 4.3 also require closing PowerPoint? Can users update in place from versions earlier than 4.3, or must they uninstall first?
- **I-Q4:** R3 says the requirements and installer changes apply to 4.4. Should the Installation chapter also keep any instructions for 4.3 or earlier (for example, the MSI package or PowerPoint 2013), or describe 4.4 only?
- **I-Q5:** After users uninstall Contoso Charts, what happens to charts in existing presentations (do they still display, and do links remain)?
- **I-Q6:** Can users reopen the Welcome pane in 4.4 after closing it? If not, should the doc say so?
- **I-Q7:** What is the procedure for a first refresh? Specifically, what do Refresh Data and Refresh All Charts each do, what's the result, and is the existing Refresh charts chapter a usable source?
- **I-Q8:** What is the procedure and result for Export to PDF? Does it export the selected chart, the slide, or the whole presentation? Is there a dialog box?
- **I-Q9:** For Link to Excel, is .xlsx the only supported format? How does the user select the range in the "Link to Excel" dialog box? Must the workbook stay in the same location for refresh to work?
- **I-Q10:** The overview article still says "Insert Chart" (R6). Is that article part of the Getting started chapter or another doc that also needs an update?

## 7. Scope check

Please confirm the doc impact list before drafting starts.

---

## Scored against the answer key

| Check | Result |
|---|---|
| All 3 superseded facts handled (latest wins, logged) | ✅ 4 logged: installer, PowerPoint, Windows 64-bit, and the label rename |
| All 4 confidential or internal items excluded (no customer name) | ✅ The code name, the performance numbers, the customer, and the IDs |
| Won't Fix, In Progress, and speculation excluded | ✅ |
| Every fact has evidence, and every pack starts with [S0] | ✅ |
| Stale install article flagged, with the reason in "Why" | ✅ |
| Gaps asked, not guessed | ⚠️ Partly. The Welcome pane is asked about (I-Q6). Nothing asks what Chart Styles and Color Palette do. |

**Beyond the answer key:** It applied the new v4 rule 13. The request named "a first refresh and export," and none of the raw sources covers it, so intake marked it **Needs source**, wrote no pack, and asked I-Q7 and I-Q8. It didn't fill the pack from general knowledge. The material exists in other chapters and in the Export article, so this is now the planner's job (planner v3, rule 16).

**Weak spot:** Packs 1 and 2 have a "Corrections" block that cites the support email (R10) as evidence. The fact itself, what the live article says, belongs in the pack. The email is a reason, though, and should only appear under "Why." The planner's inventory confirms the live article's text, so nothing is lost.
