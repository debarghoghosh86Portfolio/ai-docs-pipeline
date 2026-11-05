# Stage 5 output: Doc QA v1, round 1 (Installation and Getting started)

**Input:**

- the approved plan from [02-doc-plan.md](02-doc-plan.md), with the live titles and the guide chapter titles
- the four source packs from [01-intake-output.md](01-intake-output.md)
- the five drafts from [03-drafts.md](03-drafts.md), after the writer's edits in [04-reviews.md](04-reviews.md)

**Agent:** Doc QA v1 (`qa-agent-v1.md`). The QA project still had house-style v1.1, so the message told it to apply v1.2 rule 7.
**Run:** Claude Projects, November 2026. The release summary, doc status, and issues are copied verbatim. The link check and terminology tables are summarized.

---

## 1. Release summary

All five drafts follow their briefs closely, and every quoted UI and setup message matches the source packs exactly. However, every draft still has at least one open [GAP], so none can publish yet. Three drafts also have issues the writer can fix now: Install Contoso Charts splits wizard pages into extra steps, Create a chart leaves out the "Add your data" section and two link-map links, and Link a chart to Excel data uses chapter titles as link text. Choose a chart type has no draft because the plan held it for intake.

A note on the rule version: the project file is house-style.md v1.1. As you instructed, I applied v1.2 rule 7 (short titles and headings). All draft headings meet both versions, so no verdict depends on the choice. The project file still needs to be updated to v1.2 (QA-Q5), because it says rules change only in that file, and W-Q1 depends on which rule 7 applies.

**Ready: 0 · Ready after fixes: 0 · Blocked: 5 · Missing: 1**

## 2. Doc status

| Draft | Brief compliance | Links | Terms | Facts | Open markers | Verdict |
|---|---|---|---|---|---|---|
| System requirements (New) | ✅ | ✅ (plain text, no URL: QA-12) | ✅ | ✅ | 1 GAP (I-Q1) | Blocked |
| Install Contoso Charts (Rewrite) | Wizard pages split into extra steps (QA-3) | ✅ (plain text, no URL: QA-12) | ✅ | ✅ | 4 GAPs (I-Q1, I-Q2, I-Q3, 1 unnumbered) | Blocked |
| Contoso Charts overview (Update) | ✅ | ✅ (# placeholders: QA-12) | ✅ | Version scope of the tab groups (QA-6) | 2 GAPs (I-Q6, 1 unnumbered) | Blocked |
| Create a chart (Update) | "Add your data" and overview link not drafted (QA-7, QA-8) | 2 link-map links missing | ✅ | Lists Area, but links to an article not yet updated (QA-2) | 1 GAP (I-Q6), plus a D-Q1 reference (QA-11) | Blocked |
| Link a chart to Excel data (Update) | ✅ | 2 wrong titles (QA-9, QA-10) | Link-text convention differs from overview (QA-13) | Version scope needs confirmation (QA-6) | 1 GAP (I-Q9) | Blocked |
| Choose a chart type (Update, row 6) | No draft: held for intake | — | — | — | — | Missing (P-Q1) |

## 3. Issues

| QA-# | Draft | Check | Problem | Evidence (quote) | Fix | Needs SME? |
|---|---|---|---|---|---|---|
| QA-1 | Choose a chart type | 1 Completeness | Row 6 has the action Update but no draft. The plan holds it for intake. | Plan: "Choose a chart type \| Update \| … \| Back to intake" | No writer action. Wait for source material on the Area chart type. | Yes (P-Q1) |
| QA-2 | Create a chart | 5 Facts across articles | Create a chart lists five chart types and sends readers to Choose a chart type. That article was last updated in 2025-09 and probably doesn't cover Area. | "select Column, Bar, Line, Pie, or Area." … "For more information, see Choose a chart type." | Docs lead decides: hold Create a chart until row 6 publishes, or accept the gap for now. | Yes (P-Q1) |
| QA-3 | Install Contoso Charts | 2 Brief compliance | The brief says to give each wizard page one step. The draft splits the license page and the install-location page into two steps each, which turns 8 steps into 10. The overview link then falls in step 10, but the brief puts it in step 8. | "4. Read the license agreement, and then select I accept the agreement. 5. Select Next." and "6. Keep the default install location, or select Browse to choose another folder. 7. Select Next." | Merge steps 4 and 5, and steps 6 and 7, as Pack 2 [S2] steps 4 and 5 do. The overview link then falls in step 8. | No |
| QA-4 | Install Contoso Charts | 8 Open markers | This GAP has no question number. | "[GAP: whether the update uses the same setup wizard pages as a new installation]" | Log it as QA-Q1. | Yes |
| QA-5 | Contoso Charts overview | 8 Open markers | This GAP has no question number, and the brief doesn't ask for this content. | "[GAP: what else the Welcome pane shows]" | Log it as QA-Q2, or remove the GAP if the docs lead agrees the content is out of scope. | Maybe |
| QA-6 | Contoso Charts overview; Link a chart to Excel data | 5 and 6 Facts | Both drafts turn each pack's version line ([S0]) into a claim that the feature first appeared in 4.4. For the overview, this contradicts the brief, which keeps the four group names that already exist in the article. For Link to Excel, it's plausible (plan section 7) but not confirmed. | Overview: "In Contoso Charts 4.4 and later, the Contoso Charts tab organizes its buttons into four groups." Link: "Link to Excel is available in Contoso Charts 4.4 and later." | Confirm which items are new in 4.4 (QA-Q3). Then scope the version phrase to the buttons, or remove it. | Yes |
| QA-7 | Create a chart | 2 Brief compliance; 3a Links | The brief outlines an "Add your data" section that uses Pack 4 [S2] and links to two articles. The draft leaves the section out, so two link-map links are missing. The existing article text isn't in this QA package, so I can't tell whether it already has them. | "NOT DRAFTED (no change in the brief): the intro sentence and "## Add your data."" | Draft "Add your data" from Pack 4 [S2] with links to Enter data in the data grid and Link a chart to Excel data. Or confirm that the existing section already has both links and the Edit Data step. | No |
| QA-8 | Create a chart | 2 Brief compliance | The brief lists Contoso Charts overview under "Links out," but the draft has no link to it. This link isn't in the link map. | Brief 4: "Links out: Choose a chart type, Enter data in the data grid, Link a chart to Excel data, Contoso Charts overview" | Add the link, or confirm that the existing intro already has it. | No |
| QA-9 | Link a chart to Excel data | 3b and 3c Links | The link text is a guide chapter title, not the destination's title. "Data sources" isn't an article on the live site, and the chapter holds two articles. | "For help with a link that stops working, see Data sources." | Use the title from the link map, "Fix a broken link to an Excel workbook," until the docs lead decides W-Q1. | No (docs lead) |
| QA-10 | Link a chart to Excel data | 3b and 3c Links | The same problem: "Troubleshooting" isn't an article title on the live site. | "If a chart doesn't change after you edit the workbook, see Troubleshooting." | Use "Charts don't update after editing Excel" until the docs lead decides W-Q1. | No (docs lead) |
| QA-11 | Create a chart | 8 Open markers | The draft refers to D-Q1, but D-Q1 isn't in the plan or this QA package. | "Replaces: the existing section body, if it says "Insert Chart." See D-Q1." | Send the text of D-Q1 to QA and the docs lead. | Unknown |
| QA-12 | All drafts | 3 Links | Link markup isn't consistent. The overview uses # placeholder links, and the other drafts use plain text with no link at all. I can't confirm that any link resolves. | Overview: "Create a chart". System requirements: "For more information, see Install Contoso Charts." | Add real links with final URLs in every draft. | No |
| QA-13 | Contoso Charts overview; Link a chart to Excel data | 4 Terminology | Links to articles in finished chapters follow two conventions. The overview uses the article web titles. Link a chart to Excel data uses a web title for one link and chapter titles for the other two. The writer's note says to use chapter titles. Brief 5 also says "link to Refresh charts," but the link map says Update linked chart data. | Overview: "see Update linked chart data, and Change a chart's data source". Link: "see Update linked chart data." / "see Data sources." / "see Troubleshooting." | Pick one convention for the web and one for the guide (W-Q1, QA-Q4), and apply it in both drafts. | No (docs lead) |

## 4. Link check (summary)

There are 17 links in the link map. 12 are OK, 3 are missing from Create a chart (QA-7, QA-8), and 2 have the wrong titles in Link a chart to Excel data (QA-9, QA-10).

## 5. Terminology (summary)

Every UI label is consistent across the five drafts: the Contoso Charts tab, New Chart, Edit Data, Link to Excel, Create your first chart, ContosoChartsSetup.exe, and "Close PowerPoint to continue." QA spotted two pairs that look like duplicates but aren't, so they aren't errors:

- the Welcome **page** in setup and the Welcome **pane** in PowerPoint
- the Choose a Chart Type **dialog box** and the Choose a chart type **article**

## 6. New questions

- **QA-Q1 (SME):** Does the 4.4 update from Contoso Charts 4.3 use the same setup wizard pages as a new installation?
- **QA-Q2 (SME or docs lead):** What else does the Welcome pane show, and is it in scope for this release?
- **QA-Q3 (SME):** Which items are new in Contoso Charts 4.4: the tab's four groups, the buttons in them, the Welcome pane, or Link to Excel?
- **QA-Q4 (docs lead):** In the guide build, should link text use the guide's short titles and chapter titles, while the web keeps article titles? If a draft serves both outputs, chapter-title links don't resolve on the live site.
- **QA-Q5 (docs lead):** Update the project's house-style.md to v1.2.

## 7. Sign-off

Please review the release verdicts before publishing.

---

## Notes

**Two agents disagreed, and QA caught it.** The reviewer flagged Install steps 4 and 5 under rule 9 ("one action per step"), and I accepted the fix. QA then flagged the split under the brief, which says "give each wizard page one step." Rule 9 also says standard dialog tasks count as one action. Both readings are defensible, so the house style needs to settle it (see the resolution in [06-sme-round-and-fixes.md](06-sme-round-and-fixes.md)).

**My own edit was caught.** At the review checkpoint, I changed two links to guide chapter titles. QA flagged both (QA-9, QA-10): one draft serves both the website and the guide, and chapter titles don't resolve on the website. The publisher should convert links for each output, and the writer shouldn't.
