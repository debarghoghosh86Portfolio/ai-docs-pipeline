# Stage 2 output: Doc planner v1

**Input:** intake's doc impact, Source pack 1, and questions I-Q1 to I-Q7 (from [02-intake-output.md](02-intake-output.md), condensed), plus an inventory of 14 existing Contoso Charts articles (constructed test material: see `planning-inputs-data-refresh.md` in the portfolio).
**Agent:** Doc planner v1 (`planning-agent-v1.md`), with house-style.md v1.0
**Run:** Claude Projects, November 2026. Output copied verbatim; chat tables converted to Markdown.
**Human checkpoint:** I approved this plan as docs lead and kept the title "Update linked chart data" (P-Q3).

---

## 1. Plan summary

This plan updates six existing articles, rewrites two, and creates none. The new refresh task already has a home: "Update linked chart data" (2021-08) covers the same task, so the plan rewrites it in place and keeps its title so existing links don't break. Instead of a separate release notes article, the plan adds a 4.3 entry to "What's new in Contoso Charts." The inventory also shows a stale troubleshooting article intake couldn't see: "Charts don't update after editing Excel" says linked charts update automatically every five minutes, which contradicts [S1], so it gets a high-priority rewrite. The 4.3 messages and shortcut go into the existing "Error messages" and "Keyboard shortcuts" references.

> Note: the counts in this summary ("updates six") don't match the table below (five updates). Planner v2 added a rule that the summary must match the table.

## 2. Doc plan

| # | Title | Action | Doc type | TOC location | Priority | Effort | Order |
|---|---|---|---|---|---|---|---|
| 1 | Update linked chart data | Rewrite | Task | Work with data | High | M | 1 |
| 2 | Charts don't update after editing Excel | Rewrite | Troubleshooting | Troubleshooting | High | S | 2 |
| 3 | Link a chart to Excel data | Update | Task | Work with data | High | S | 3 |
| 4 | Error messages | Update | Reference | Reference | Medium | S | 4 |
| 5 | Keyboard shortcuts | Update | Reference | Reference | Low | S | 5 |
| 6 | Enter data in the data grid | Update | Task | Create charts | Low | S | 6 |
| 7 | What's new in Contoso Charts | Update | Reference | Getting started | Medium | S | 7 |
| 8 | Fix a broken link to an Excel workbook | No change (link target; SME to confirm accuracy, see section 7) | Task | Troubleshooting | — | — | — |
| 9 | Change a chart's data source | No change (link target) | Task | Work with data | — | — | — |
| 10 | Contoso Charts overview | No change (writer to verify; see section 6) | Concept | Getting started | — | — | — |

Order rationale: doc 1 is the main link target, so it comes first. "What's new" links to almost everything, so it comes last.

## 3. Changes to intake's plan

| Intake row | Intake said | Plan says | Reason |
|---|---|---|---|
| 1 | New: "Refresh a chart linked to Excel data" | Rewrite: "Update linked chart data" (same location, same title) | The existing article covers the same task (getting current Excel data into a linked chart). A new article would duplicate it. Its 2021 content (close and reopen the presentation) is outdated. The title is sentence case, starts with a verb, and still fits, so keeping it protects existing links. See P-Q3. |
| 3 | Update keyboard shortcuts reference "if one exists" | Update: "Keyboard shortcuts" | The article exists (Reference section, 2025-06). This answers I-Q7. |
| 4 | Action "Release note": new "Contoso Charts 4.3 release notes" | Update: "What's new in Contoso Charts" (add a 4.3 entry) | Release notes live in one article organized by version. The latest entry is 4.2. |
| — (not in intake) | — | Rewrite: "Charts don't update after editing Excel" | Says charts update automatically every five minutes, which contradicts [S1]. |
| — (not in intake) | — | Update: "Error messages" | The reference lists every message. It needs the 4.3 "chart is full" warning ([S4]) and possibly the workbook message (P-Q5). |
| — (not in intake) | — | Update: "Enter data in the data grid" | Readers choosing between data grid and Excel need to know that grid charts can't be refreshed ([S2]). |

## 4. Drafting briefs

### Brief 1

```
Title: Update linked chart data
Action: Rewrite
Doc type: Task
TOC location: Work with data
Outline:
- Intro: what refresh does; refresh is manual; formatting is kept; available in Contoso Charts 4.3 and later — uses [S0], [S1]
- Before you begin: chart must be linked to an .xlsx workbook; data grid charts can't be refreshed; save the workbook first because refresh reads the last saved version — uses [S2]
- Refresh the selected chart: Refresh Data in the Data group on the Contoso Charts tab, or Ctrl+Alt+R — uses [S3]
- Refresh all linked charts in a presentation: Refresh All Charts in the same group — uses [S3] (behavior for unlinked charts pending I-Q4)
- Messages you might see: workbook not found; chart is full — uses [S4]
- Related articles
Links out: Link a chart to Excel data; Fix a broken link to an Excel workbook; Change a chart's data source; Error messages; Keyboard shortcuts.
What to change, keep, and remove: Replace the whole body. Remove "close and reopen the presentation" as the method, unless P-Q1 confirms it still works. If so, keep it only as a version-specific note for versions before Contoso Charts 4.3. Keep the title and TOC location. Use the word "refresh" in the intro so search finds the article.
Source pack: Source pack 1
```

### Brief 2

```
Title: Charts don't update after editing Excel
Action: Rewrite
Doc type: Troubleshooting. The Doc drafter has no Troubleshooting template, so use the Task template with symptom, cause, and fix headings; see P-Q4.
TOC location: Troubleshooting
Outline:
- Symptom: a linked chart still shows old data after you edit the Excel workbook
- Cause: charts don't update automatically — uses [S1]
- Fix: refresh the chart — uses [S3]; link to Update linked chart data
- Cause: the workbook has unsaved changes. Fix: save the workbook, then refresh — uses [S2]
- Cause: the chart's data was entered in the data grid, not linked. Fix: link the chart to Excel data — uses [S2]
- Cause: the workbook was moved or deleted. Fix: relink the chart — uses [S4]; link to Fix a broken link to an Excel workbook
Links out: Update linked chart data; Link a chart to Excel data; Fix a broken link to an Excel workbook.
What to change, keep, and remove: Remove "This is expected," "update automatically every 5 minutes," "Wait," and "close and reopen" (pending P-Q1 and P-Q2). Keep the title, because it describes the symptom readers search for.
Source pack: Source pack 1 (intake didn't assign a pack to this doc)
```

### Brief 3

```
Title: Link a chart to Excel data
Action: Update
Doc type: Task
TOC location: Work with data
Outline: existing outline stays. Change one passage — uses [S1], [S0]
Links out: add Update linked chart data.
What to change, keep, and remove: Remove "Your chart updates automatically when the Excel data changes." Replace it with a sentence that says charts don't update automatically and links to Update linked chart data. Which versions the correction applies to is pending I-Q1. Keep the linking steps. The supported formats statement is pending I-Q5.
Source pack: Source pack 2
```

### Brief 4

```
Title: Error messages
Action: Update
Doc type: Reference
TOC location: Reference
Outline:
- Add entry: "Some data wasn't added because the chart is full." Cause: more rows than series slots; extra rows are ignored — uses [S4]. The fix depends on the I-Q3 answer.
- Add or verify entry: "Can't find the linked workbook. Use Change Source to relink it." Cause: workbook moved or deleted. Fix: link to Fix a broken link to an Excel workbook — uses [S4]. See P-Q5.
Links out: Fix a broken link to an Excel workbook; Update linked chart data.
What to change, keep, and remove: Add the entries in the article's existing order and format. Don't change other entries.
Source pack: Source pack 1 ([S4])
```

### Brief 5

```
Title: Keyboard shortcuts
Action: Update
Doc type: Reference
TOC location: Reference
Outline:
- Under the Contoso Charts tab group, add Ctrl+Alt+R: refresh the selected linked chart (Contoso Charts 4.3 and later) — uses [S3], [S0]
Links out: add Update linked chart data.
What to change, keep, and remove: Add one row. Mac equivalent pending I-Q6. Keep everything else.
Source pack: Source pack 3
```

### Brief 6

```
Title: Enter data in the data grid
Action: Update
Doc type: Task
TOC location: Create charts
Outline:
- Add one note: charts with data entered in the data grid can't be refreshed from Excel; to keep a chart in sync with a workbook, link it instead — uses [S2]
Links out: add Link a chart to Excel data.
What to change, keep, and remove: Add the note only. Keep the existing steps.
Source pack: Source pack 1 ([S2])
```

### Brief 7

```
Title: What's new in Contoso Charts
Action: Update
Doc type: Reference
TOC location: Getting started
Outline:
- New "Contoso Charts 4.3" entry, above 4.2: refresh linked charts manually with Refresh Data, Refresh All Charts, or Ctrl+Alt+R — uses [S0], [S3]
- Behavior note: linked charts don't update automatically — uses [S1]. Whether to frame this as a correction or a change depends on P-Q2.
Links out: Update linked chart data; Keyboard shortcuts.
What to change, keep, and remove: Add the 4.3 entry. Don't edit earlier entries.
Source pack: Source pack 4
```

## 5. Link map

| From article | To article | Why |
|---|---|---|
| Link a chart to Excel data | Update linked chart data | Next step after linking; replaces the incorrect automatic-update claim |
| Charts don't update after editing Excel | Update linked chart data | Main fix |
| Charts don't update after editing Excel | Fix a broken link to an Excel workbook | Fix for a moved or deleted workbook |
| Charts don't update after editing Excel | Link a chart to Excel data | Fix for data grid charts |
| Update linked chart data | Link a chart to Excel data | Prerequisite |
| Update linked chart data | Fix a broken link to an Excel workbook | Workbook-not-found message |
| Update linked chart data | Change a chart's data source | Related task in the same Data group |
| Update linked chart data | Error messages | Full list of messages |
| Update linked chart data | Keyboard shortcuts | Ctrl+Alt+R |
| Error messages | Fix a broken link to an Excel workbook | Fix for the workbook-not-found message |
| Error messages | Update linked chart data | Context for both refresh messages |
| Keyboard shortcuts | Update linked chart data | Context for Ctrl+Alt+R |
| Enter data in the data grid | Link a chart to Excel data | Alternative for readers who need refresh |
| What's new in Contoso Charts | Update linked chart data | Feature announcement |
| What's new in Contoso Charts | Keyboard shortcuts | New shortcut |

## 6. Stale or conflicting content found

| Article | Problem | Recommended action |
|---|---|---|
| Charts don't update after editing Excel (2022-05) | Says linked charts update automatically every five minutes. Contradicts [S1]. Not in intake's list. | Rewrite (doc 2). High priority, because readers land here when they hit the problem. |
| Link a chart to Excel data (2024-11) | Says charts update automatically. Contradicts [S1]. | Update (doc 3) |
| Update linked chart data (2021-08) | Tells readers to close and reopen the presentation. Doesn't mention refresh. | Rewrite (doc 1); keep or drop the old method based on P-Q1 |
| What's new in Contoso Charts (2026-03) | Latest entry is 4.2. | Update (doc 7) |
| Keyboard shortcuts (2025-06) | Missing Ctrl+Alt+R. | Update (doc 5) |
| Error messages (2025-10) | Likely missing the 4.3 "chart is full" warning. | Update (doc 4) |
| Contoso Charts overview (2025-06) | Describes the Data group. If it lists the group's commands, it's missing Refresh Data and Refresh All Charts. | Writer checks the article. If it lists commands, add both buttons (Update, S). |
| Fix a broken link to an Excel workbook (2023-01) and Change a chart's data source (2025-02) | Both describe Change Source procedures. This overlaps, and the 2023 steps might be older than the 2025 ones. | No change this cycle. Confirm accuracy (I-Q2). Consider a merge in a later cycle (P-Q6). |

## 7. Questions

### New questions

- **P-Q1 (SME):** In Contoso Charts 4.3, does closing and reopening a presentation still load the current Excel data? Did it in earlier versions? The answer decides whether "Update linked chart data" and the troubleshooting article keep this method, and for which versions.
- **P-Q2 (SME):** Did linked charts ever update automatically, for example every five minutes, in any version? If yes, the 4.3 entry in "What's new" describes a behavior change. If no, the old articles were wrong, and the entry only needs to describe the new feature.
- **P-Q3 (docs lead):** Keep the title "Update linked chart data," or retitle it to "Refresh linked chart data" to match the UI? Retitling would need a redirect. The plan keeps the current title.
- **P-Q4 (docs lead):** The Doc drafter has no Troubleshooting template. Is it OK to use the Task template with symptom, cause, and fix headings for doc 2?
- **P-Q5 (SME):** Is "Can't find the linked workbook. Use Change Source to relink it." new in Contoso Charts 4.3, or is it already in "Error messages"?
- **P-Q6 (docs lead):** Should "Fix a broken link to an Excel workbook" and "Change a chart's data source" be merged in a later cycle? If yes, which one should survive?

### Intake questions that existing docs might answer

| I-Q# | Existing article | Confirm with SME |
|---|---|---|
| I-Q2 | "Change a chart's data source" (says Change Source is in the Data group) and "Fix a broken link to an Excel workbook" (relink steps) | Are the relink steps from 2023-01 still accurate in Contoso Charts 4.3? If yes, link to them instead of adding a GAP. |
| I-Q6 | "Keyboard shortcuts" (lists all shortcuts by tab, possibly including Mac equivalents) | Does the article list Mac shortcuts? If it does, what's the Mac equivalent of Ctrl+Alt+R? |
| I-Q7 | "Keyboard shortcuts" (Reference section) | Answered by the inventory. No SME check needed. |

I-Q1, I-Q3, I-Q4, and I-Q5 aren't answered by any existing article and stay open.

## 8. Approval

Please approve the doc plan before drafting starts.
