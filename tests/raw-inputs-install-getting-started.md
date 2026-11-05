# Raw inputs: Installation and Getting started (Contoso Charts 4.4)

Test material for Doc intake v4. Written by hand, with traps planted on purpose.
Paste everything below the line into the Doc intake project.

---

DOC REQUEST (not a product change). Prepare source packs for the
Installation and Getting started chapters of the Contoso Charts 4.4 User Guide.

[R1] Docs lead request — Jan 19
"Assemble the full Contoso Charts 4.4 User Guide. Chapter order: What's new,
Installation, Getting started, then the existing chapters (Refresh charts,
Data sources, Troubleshooting, Reference). Installation covers requirements,
install, update, and uninstall. Getting started covers the Contoso Charts tab,
creating a chart, linking it to Excel, and a first refresh and export."

[R2] Installer spec v1 (PM) — Sep 3, 2025
- Installer file: ContosoCharts-Installer.msi
- Requires PowerPoint 2013 or later.
- Windows 10 or Windows 11.

[R3] Installer spec v2 (PM) — Jan 14. "Supersedes v1."
- The installer is now a single file: ContosoChartsSetup.exe. The MSI package
  is dropped in 4.4.
- Requires PowerPoint 2016 or later. PowerPoint 2013 support is dropped in 4.4.
- Windows 10 or Windows 11, 64-bit.
- You need administrator rights on the computer to install.
- Internal: the new installer's code name is "Kestrel."

[R4] QA test script TS-INSTALL-44 — Status: Passed, build 4.4
Install (new computer):
1. Close PowerPoint. (If PowerPoint is open, setup shows "Close PowerPoint to
   continue." and waits.)
2. Double-click ContosoChartsSetup.exe.
3. On the Welcome page, select Next.
4. Read the license agreement, select "I accept the agreement," then Next.
5. Keep the default install location, or select Browse to choose another
   folder. Select Next.
6. Select Install. A progress bar shows the installation status.
7. Select Finish.
8. Open PowerPoint. The Contoso Charts tab appears on the ribbon. The first
   time, the Welcome pane opens on the right.
Update (4.3 installed): run the 4.4 setup file. It upgrades in place. You
don't need to uninstall 4.3 first. Existing linked charts keep their links.
Passed.
Uninstall:
- Windows 11: Settings > Apps > Installed apps > Contoso Charts > More (...) >
  Uninstall. Passed.
- Windows 10: Control Panel > Programs > Programs and Features > Contoso
  Charts > Uninstall. Passed.
Tester note: "Install took 48 s on the test VM; target is under 30 s."

[R5] UI spec, Contoso Charts tab (design) — Jan 9. Confirmed in build 4.4.
| Group | Buttons |
| Create | New Chart, Edit Data (opens the data grid) |
| Data | Link to Excel, Refresh Data, Refresh All Charts, Change Data Source |
| Format | Chart Styles, Color Palette |
| Export | Export to PDF |

[R6] Slack, #contoso-charts-docs — Jan 16
- Writer: "The overview article still says Insert Chart."
- Designer: "Insert Chart was the old name. It's New Chart in the 4.4 build."
- Designer: "The Welcome pane opens only the first time. Its 'Create your first
  chart' button does the same as New Chart."
- PM: "We might add a Help > Welcome menu item later so people can reopen it."

[R7] Feature spec: Create and link charts (PM) — Jan 10. Status: Approved,
shipped in 4.4.
Create a chart:
- On the Contoso Charts tab, in the Create group, select New Chart. The
  "Choose a Chart Type" dialog box opens.
- Chart types: Column, Bar, Line, Pie, Area.
- Select a chart type, then select Insert. The chart appears on the slide
  with sample data.
- To change the data of a chart that isn't linked, select the chart, then
  select Edit Data. The data grid opens.
Link a chart to Excel:
- Select the chart. On the Contoso Charts tab, in the Data group, select Link
  to Excel. The "Link to Excel" dialog box opens.
- Browse to the workbook (.xlsx), select the range, then select OK. The chart
  shows the data from that range.
- After you link a chart, Edit Data is unavailable for it. Change the data in
  Excel instead, then refresh.

[R8] Jira CCH-1402 — "Per-user install without administrator rights."
Status: Won't Fix.

[R9] Jira CCH-1410 — "Publish Contoso Charts on AppSource." Status: In
Progress. Target 4.5.

[R10] Support email — Jan 15. From the IT team at Northwind Traders:
"Several of our staff installed Contoso Charts and then couldn't find the tab.
It turned out PowerPoint was open during setup. Your install article doesn't
mention closing PowerPoint, and it still says PowerPoint 2013 works."
