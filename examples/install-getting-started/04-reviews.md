# Stage 4 output: Style guide reviewer v5, five reviews against house-style v1.2

**Input:** the five drafts in [03-drafts.md](03-drafts.md)
**Agent:** Style guide reviewer v5 (`style-reviewer-v5.md`), with house-style.md v1.2
**Run:** Claude Projects, November 2026. Five runs, one chat per draft. The issue tables are copied verbatim. The summaries are shortened.

---

## Summary

| Draft | Issues | High | Medium | Low | Main finding |
|---|---|---|---|---|---|
| System requirements | 0 | 0 | 0 | 0 | Clean against all 23 rules |
| Install Contoso Charts | 2 | 0 | 2 | 0 | Two wizard steps combine an action with **Next** (rule 9) |
| Contoso Charts overview | 2 | 0 | 2 | 0 | Is "Welcome" an on-screen label that should be bold? (rule 8, pending Q1) |
| Create a chart | 2 | 0 | 2 | 0 | The same "Welcome pane" bold question |
| Link a chart to Excel data | 2 | 0 | 2 | 0 | **Link text uses destination titles that now break rule 7** |

**Total: 8 issues across 4 drafts. No High-severity issues.**

## Install Contoso Charts: issues table

| # | Location | Original text | Issues | Rules | Suggested fix | Severity |
|---|---|---|---|---|---|---|
| 1 | Install, step 4 | Read the license agreement, select **I accept the agreement**, and then select **Next**. | The step has more than one action: accepting the agreement and moving to the next page. | 9 | 4. Read the license agreement, and then select **I accept the agreement**. 5. Select **Next**. Renumber the later steps. | Medium |
| 2 | Install, step 5 | Keep the default install location, or select **Browse** to choose another folder. Then select **Next**. | The step has two actions: choosing a location and moving to the next page. Choosing a folder through Browse is a standard dialog task, so it counts as one action. Next is a separate action. | 9 | Keep the default install location, or select **Browse** to choose another folder. Select **Next** (as its own step). Renumber the later steps. | Medium |

Writer question Q1: After you select Uninstall, does a confirmation prompt appear? If it does, add the next action or the result (rule 10).

## Contoso Charts overview and Create a chart: issues table (same pattern)

| # | Location | Original text | Issues | Rules | Suggested fix | Severity |
|---|---|---|---|---|---|---|
| 1 | Welcome pane, paragraph 1 | "…the Welcome pane opens on the right…" | "Welcome" might be the pane's on-screen label. If it is, it isn't bold, but the dialog box name in the same article is. | 8 | Pending Q1 | Medium |
| 2 | Welcome pane, paragraph 2 | "…Create your first chart button on the Welcome pane…" | Same as row 1. | 8 | Pending Q1 | Medium |

Writer question Q1: Is "Welcome" the literal on-screen title of the pane? The overview reviewer also asked for the "What Contoso Charts does" section, so it could confirm the Insert Chart change there.

## Link a chart to Excel data: issues table

| # | Location | Original text | Issues | Rules | Suggested fix | Severity |
|---|---|---|---|---|---|---|
| 1 | After you link, second link sentence | "For help with a link that stops working, see Fix a broken link to an Excel workbook." | The link text is the destination title, which has 7 words. Titles must never have more than 6. | 7, 23 | Pending Q1 | Medium |
| 2 | After you link, third link sentence | "If a chart doesn't change after you edit the workbook, see Charts don't update after editing Excel." | The link text is the destination title, which reads as a sentence (a statement of the symptom). Rule 7 says a heading is a label, not a sentence. | 7, 23 | Pending Q1 | Medium |

Writer question Q1: Are these the final published titles? If they change to meet rule 7, update the link text to match. "Don't change the link text on its own, or it won't match the destination."

---

## Human checkpoint: writer's edits before QA

| Review finding | Writer decision |
|---|---|
| Install, steps 4–5 (rule 9) | **Accepted.** Steps 4 and 5 are split, so the procedure now has 10 steps. |
| "Welcome pane" bold (rule 8) | **Not bold.** In the sources it's a descriptive name, not a quoted label. For consistency, the bold on "**Welcome** pane" and "**Welcome** page" is also removed from the Install draft. |
| Link titles break rule 7 | **Accepted for the guide.** In the guide, links point to the short chapter titles ("Data sources," "Troubleshooting"). The web article titles are a separate decision, logged for the docs lead as **W-Q1**. |
| Uninstall confirmation (Q1) | Added to the SME list as D-Q3, already asked by the drafter |

## Scored against the answer key

| Check | Result |
|---|---|
| Flags long or sentence-style headings (v1.2, rule 7) | ✅ It caught the rule through *link text*, which nobody planted: two live article titles now break the new rule. |
| Doesn't flag the kept web titles of 4–6 words | ✅ "Install Contoso Charts" and "Link a chart to Excel data" pass |
| Few issues, because the drafter follows the same house style | ✅ 8 Medium-severity issues and no High ones, compared with 27 on the legacy page in Part 1 |

**Beyond the answer key:** changing one rule in house-style.md affected every agent that reads it. The reviewer applied rule 7 to link text and found that two finished articles' titles are now non-compliant. One edit to a shared rules file is enough to surface a site-wide rename question.
