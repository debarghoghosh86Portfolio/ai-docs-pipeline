# Stage 2 output: Doc planner v3, Contoso Charts 4.4 User Guide (full guide scope)

**Input:** the request and inventory in `planning-inputs-install.md`, plus intake v4's output from [01-intake-output.md](01-intake-output.md). The doc impact list was confirmed at the first human checkpoint.
**Agent:** Doc planner v3 (`planning-agent-v3.md`), with house-style.md v1.2
**Run:** Claude Projects, November 2026. The output is copied verbatim, with chat tables converted to Markdown.
**Human checkpoint:** I approved this plan as docs lead. On P-Q2, Choose a chart type, Enter data, and Export to PDF stay in Getting started. Choose a chart type is held for intake.

---

## 1. Plan summary

This plan assembles the Contoso Charts 4.4 User Guide from five finished chapters and two chapters still to draft: Installation and Getting started. The work is one new article, one rewrite, and four updates. One of the updates goes back to intake for source material. Two existing articles are placed in the guide with no change. The biggest structural decision is that Getting started reuses existing articles instead of adding new ones. The overview, Create a chart, and Link a chart to Excel data articles already cover intake’s rows 3 and 4. Intake’s “First refresh and export” row is replaced by links to the finished Refresh charts chapter and the existing Export charts to PDF article. Installation splits into a new System requirements reference and a rewrite of Install Contoso Charts that keeps its URL.

## 2. Guide outline
| # | Chapter | Built from (existing articles) | Status |
|---|---|---|---|
| 1 | What’s new | What’s new in Contoso Charts (4.3 and 4.4 entries) | Done |
| 2 | Installation | System requirements (New, row 1); Install Contoso Charts (Rewrite, row 2) | Draft |
| 3 | Getting started | Overview (row 3); Create a chart (row 4); Choose a chart type (row 6); Enter data (row 7); Link to Excel (row 5); Export to PDF (row 8) | Draft (Choose a chart type: Needs source) |
| 4 | Refresh charts | Update linked chart data | Done |
| 5 | Data sources | Change a chart’s data source; Fix a broken link to an Excel workbook | Done |
| 6 | Troubleshooting | Charts don’t update after editing Excel | Done |
| 7 | Reference | Error messages; Keyboard shortcuts | Done |

Chapter 3 orders its articles so a new user creates a chart, adds data, and exports it. The last article in the chapter links forward to Refresh charts. The requested chapter order has no home for Choose a chart type, Enter data in the data grid, or Export charts to PDF, so this plan places them in Getting started (see P-Q2).

## 3. Doc plan
| # | Title (web / guide) | Action | Doc type | TOC location | Priority | Effort | Order |
|---|---|---|---|---|---|---|---|
| 1 | System requirements | New | Reference | Getting started (guide: Installation) | High | S | 1 |
| 2 | Install Contoso Charts | Rewrite | Task | Getting started (guide: Installation) | High | M | 2 |
| 3 | Contoso Charts overview / Overview | Update | Concept | Getting started | Medium | S | 5 |
| 4 | Create a chart | Update | Task | Create charts (guide: Getting started) | High | S | 3 |
| 5 | Link a chart to Excel data / Link to Excel | Update | Task | Work with data (guide: Getting started) | High | S | 4 |
| 6 | Choose a chart type | Update | Concept | Create charts (guide: Getting started) | Low | S | Back to intake |
| 7 | Enter data in the data grid / Enter data | No change | Task | Create charts (guide: Getting started) | — | — | — |
| 8 | Export charts to PDF / Export to PDF | No change | Task | Export and share (guide: Getting started) | — | — | — |

The rows break down as one New, one Rewrite, four Update, and two No change.

On the order: System requirements is the only new link target, so it goes first. Every other link target keeps its existing title and URL, so after row 1 the order follows priority. Install comes next because of the support request.

Where web and guide titles differ, the web title and URL stay as they are. Only the guide uses the shorter title. The shorter guide titles keep the sibling task headings in Getting started parallel: “Create a chart,” “Choose a chart type,” “Enter data,” “Link to Excel,” and “Export to PDF.”

## 4. Changes to intake’s plan
| Intake row | Intake said | Plan says | Reason |
|---|---|---|---|
| 1 | Update “Installation: System requirements” (Reference) | New “System requirements” (Reference) | No requirements article exists. The requirement sentence is inside Install Contoso Charts and moves to the new article. A separate article keeps the Reference and Task doc types apart. |
| 2 | Update “Install, update, and uninstall Contoso Charts” | Rewrite “Install Contoso Charts” (keep title and URL) | Most of the content is replaced: the installer, the requirements, and every step. The update and uninstall sections are new. Intake’s title has six words, at the limit of rule 7. The existing title and URL still fit, and the first sentence states the full scope. |
| 3 | New “The Contoso Charts tab and Welcome pane” (Reference) | Update “Contoso Charts overview” (Concept) | The overview already describes the tab and its four groups, so a new article would duplicate it. The article keeps its Concept type and gains a table of buttons. This also answers I-Q10: the overview is in scope. |
| 4 | New “Create a chart and link it to Excel” | Update “Create a chart” and update “Link a chart to Excel data” | Both articles exist, and creating and linking are separate tasks (rule 8). The linking steps are also stale (see section 7). |
| 5 | Needs source “First refresh and export” | No new article. Link to the Refresh charts chapter, and place Export charts to PDF in Getting started with no change. | Both procedures already exist in articles updated in Jan 2027. Refresh and export are separate tasks (rule 8). This answers I-Q7 and I-Q8, pending SME confirmation. |
| — | Not listed | Choose a chart type: Update, back to intake | The article is probably missing the Area chart type (see section 7). |
| — | Not listed | Enter data in the data grid: No change, placed in Getting started | Create a chart links to it for charts that aren’t linked to Excel. |

## 5. Drafting briefs

### Brief 1

Title: System requirements
Action: New
Doc type: Reference
TOC location: Getting started (live site); guide: Installation, first article
Outline:
Intro sentence (“This article lists what you need to install Contoso Charts 4.4.”) — uses Pack 1 [S0]
Requirements — uses Pack 1 [S1], [S3]. Use a table with three rows: operating system, PowerPoint version, and permissions. Per [S3], don’t say that PowerPoint 2013 works. State that Contoso Charts 4.4 doesn’t support it.
Installer file — uses Pack 1 [S2]
Links out: Install Contoso Charts
Source pack: Pack 1
Already asked: I-Q1, I-Q2, I-Q4, P-Q3, P-Q6

### Brief 2

Title: Install Contoso Charts (same title on the web and in the guide; keep the URL)
Action: Rewrite
Doc type: Task
TOC location: Getting started (live site); guide: Installation, second article
Outline:
Intro sentence (“This article explains how to install, update, and uninstall Contoso Charts 4.4.”) — uses Pack 2 [S0]
Before you install — uses Pack 2 [S1]. Link to System requirements.
Install — uses Pack 2 [S2]. Steps 3 to 7 are wizard pages; give each page one step. Put each result in the same step as its action. Step 8 links to Contoso Charts overview for the tab and the Welcome pane.
Update — uses Pack 2 [S3]. Name the product with its version (“Contoso Charts 4.3”).
Uninstall — uses Pack 2 [S4]. Use one short procedure each for Windows 11 and Windows 10.
Links out: System requirements, Contoso Charts overview, Create a chart
What to change, keep, and remove:
Change: Replace ContosoCharts-Installer.msi with ContosoChartsSetup.exe. Replace the wizard steps with Pack 2 [S2]. Add the close-PowerPoint step (Pack 2 [S5]).
Keep: The title and URL.
Remove: “Requires PowerPoint 2013 or later.” The requirements now live in System requirements.
Add: The Update and Uninstall sections.
Source pack: Pack 2 (Pack 1 [S1] only for the link to requirements)
Already asked: I-Q1, I-Q2, I-Q3, I-Q4, I-Q5, P-Q5, P-Q6

### Brief 3

Title: Contoso Charts overview (guide: Overview)
Action: Update
Doc type: Concept
TOC location: Getting started; guide: Getting started, first article
Outline:
What Contoso Charts does — keep the existing content (no new source)
Contoso Charts tab — uses Pack 3 [S0], [S1]. Use a table with one row per group (Create, Data, Format, Export) listing its buttons.
Welcome pane — uses Pack 3 [S2]
Links out: Create a chart, Enter data in the data grid, Link a chart to Excel data, Update linked chart data (Refresh charts chapter), Change a chart’s data source (Data sources chapter), Export charts to PDF
What to change, keep, and remove:
Change: “Insert Chart” to New Chart (decision log).
Keep: The product description and the four group names.
Remove: “Select Insert Chart to add a chart.” Replace it with a link to Create a chart.
Add: The buttons in each group and the Welcome pane section.
Source pack: Pack 3
Already asked: I-Q6, I-Q10

### Brief 4

Title: Create a chart
Action: Update
Doc type: Task
TOC location: Create charts; guide: Getting started
Outline:
Intro sentence — uses Pack 4 [S0]
Create a chart (procedure) — uses Pack 4 [S1]. Cover New Chart, the Choose a Chart Type dialog box, all five chart types, and Insert. The result is a chart with sample data.
Use the Welcome pane — uses Pack 4 [S1] (last bullet), Pack 3 [S2]
Add your data — uses Pack 4 [S2]. Link to Enter data in the data grid and to Link a chart to Excel data.
Links out: Choose a chart type, Enter data in the data grid, Link a chart to Excel data, Contoso Charts overview
What to change, keep, and remove:
Change: “Insert Chart” to New Chart. Add Area to the chart types.
Keep: The link to Choose a chart type.
Remove: Every “Insert Chart” reference.
Source pack: Pack 4 (and Pack 3 [S2])
Already asked: I-Q6, I-Q10, P-Q1

### Brief 5

Title: Link a chart to Excel data (guide: Link to Excel)
Action: Update
Doc type: Task
TOC location: Work with data; guide: Getting started
Outline:
Intro sentence — uses Pack 4 [S0]
Link a chart (procedure) — uses Pack 4 [S3]
After you link — uses Pack 4 [S4]. Keep the existing sentence that linked charts don’t update automatically, and link to Refresh charts.
Links out: Update linked chart data (Refresh charts chapter), Fix a broken link to an Excel workbook (Data sources chapter), Charts don’t update after editing Excel (Troubleshooting)
What to change, keep, and remove:
Change: Replace the 2024 “Select Data > From Excel” steps with the Link to Excel procedure from [S3].
Keep: The refresh note.
Remove: The old UI path.
Add: The fact that Edit Data is unavailable after linking.
Source pack: Pack 4
Already asked: I-Q7, I-Q9

Back to intake: Choose a chart type (row 6). There’s no brief for this article. It needs source material describing the Area chart type and when to use it, in the same depth as the other four types (P-Q1).

## 6. Link map
| From article | To article | Why |
|---|---|---|
| Install Contoso Charts | System requirements | Check requirements before installing |
| System requirements | Install Contoso Charts | Next step |
| Install Contoso Charts | Contoso Charts overview | Explains the tab and the Welcome pane that appear after step 8 |
| Install Contoso Charts | Create a chart | First task after installing |
| Contoso Charts overview | Create a chart | New Chart button |
| Contoso Charts overview | Enter data in the data grid | Edit Data button |
| Contoso Charts overview | Link a chart to Excel data | Link to Excel button |
| Contoso Charts overview | Update linked chart data | Refresh Data and Refresh All Charts buttons |
| Contoso Charts overview | Change a chart’s data source | Change Data Source button |
| Contoso Charts overview | Export charts to PDF | Export to PDF button |
| Create a chart | Choose a chart type | Help choosing a type |
| Create a chart | Enter data in the data grid | Replace the sample data |
| Create a chart | Link a chart to Excel data | Use Excel data instead |
| Link a chart to Excel data | Update linked chart data | Linked charts need a refresh |
| Link a chart to Excel data | Fix a broken link to an Excel workbook | The workbook moved or was renamed |
| Link a chart to Excel data | Charts don’t update after editing Excel | Stale data |

## 7. Stale or conflicting content found
| Article | Problem | Recommended action |
|---|---|---|
| Install Contoso Charts | It names ContosoCharts-Installer.msi and says PowerPoint 2013 works. It has no close-PowerPoint step and no update or uninstall steps. All of this contradicts Packs 1 and 2. | Rewrite (row 2) |
| Contoso Charts overview | It says “Insert Chart.” The button is now New Chart (decision log). | Update (row 3) |
| Create a chart | It says “Insert Chart” and lists four chart types. Version 4.4 has five, adding Area (Pack 4 [S1]). | Update (row 4) |
| Link a chart to Excel data | Its 2024 steps use “Select Data > From Excel.” Version 4.4 uses Link to Excel in the Data group (Pack 4 [S3]). Intake didn’t flag this. | Update (row 5) |
| Choose a chart type | It was last updated in 2025-09, along with Create a chart, so it probably doesn’t cover Area. | Update after new source (row 6, P-Q1) |

## 8. Questions

P-Q1 (SME): Choose a chart type needs an Area entry. What is the Area chart for, and how does it compare with the other four types?

P-Q2 (docs lead): The requested chapter order has no chapter for Choose a chart type, Enter data in the data grid, or Export charts to PDF. This plan places them in Getting started. Do you want that, or should the guide add chapters such as “Create charts” and “Export”?

P-Q3 (docs lead): Does the finished What’s new 4.4 entry mention these changes: the new installer, PowerPoint 2016 or later, 64-bit Windows, and administrator rights? If it doesn’t, the entry needs an addition before the guide ships.

P-Q4 (SME): Enter data in the data grid was last updated in 2026-11. Does it open the grid with Edit Data, and does it mention “Insert Chart” anywhere?

P-Q5 (docs lead): Error messages and Troubleshooting are both finished chapters. Should Error messages add the setup message “Close PowerPoint to continue.”? Should Troubleshooting add a “Missing tab” section? This is your call, because changing them would reopen done chapters.

P-Q6 (docs lead): On the live site, System requirements and Install Contoso Charts stay in the Getting started section, but the guide puts them in an Installation chapter. Should the site add an Installation section to match?

Intake questions that existing docs may answer:
| I-Q# | Existing article | Confirm with SME |
|---|---|---|
| I-Q7 | Update linked chart data (Refresh charts chapter) | Confirm that it covers both Refresh Data and Refresh All Charts for 4.4, with results. If so, Getting started links to it. |
| I-Q8 | Export charts to PDF | It says you can export “up to 50 charts.” Confirm what gets exported (the selected charts, the slide, or the presentation) and whether there’s a dialog box. |
| I-Q9 | Link a chart to Excel data; Fix a broken link to an Excel workbook; Charts don’t update after editing Excel | Confirm that the existing range-selection text still applies in 4.4. Confirm that the workbook must stay in the same location, and that you relink with Change Data Source. |
| I-Q10 | Contoso Charts overview | This plan answers the scope part (Update, row 3). Confirm that the button rename is the only 4.4 change to the article. |

## 9. Approval

Please approve the doc plan before drafting starts.

---

## Scored against the answer key

| Check | Result |
|---|---|
| Guide outline in the requested chapter order | ✅ |
| No duplicates: the four existing articles are reused | ✅ Overview, Create a chart, and Link a chart are updated. Intake's two "New" rows are overridden. |
| Stale articles flagged | ✅ All 4: Install, Overview, Create a chart, and Link a chart. Link a chart was flagged even though intake missed it. Choose a chart type is flagged as possibly stale. |
| Done chapters placed, not re-planned | ✅ |
| Titles and headings short (rule 7, v1.2) | ✅ Every web title is kept, and the shorter guide titles ("Overview," "Link to Excel") are listed next to them. |
| Briefs list "Already asked" | ✅ |
| Summary counts match the table | ✅ 1 New, 1 Rewrite, 4 Update, 2 No change |

**Rule 16 at work:** intake's "Needs source" row, "First refresh and export," got no brief. The planner noticed that both procedures already exist in finished articles. It linked to them and asked the SME to confirm (I-Q7, I-Q8). Then it found a new sourceless item, the Area entry in Choose a chart type, and sent that back to intake instead of briefing it.

**Beyond the answer key:** P-Q3 noticed that the finished What's new 4.4 entry doesn't mention the installer and requirement changes. P-Q5 asked whether the setup message belongs in Error messages, without reopening done chapters on its own.

**One judgment call:** System requirements was split out as a New Reference article. That's defensible, but the guide could just as well keep requirements as a section of Install. The docs lead accepted the split.
