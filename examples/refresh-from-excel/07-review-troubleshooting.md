# Stage 4 output: Style guide reviewer v5 — "Charts don't update after editing Excel"

**Input:** the draft in [06-draft-troubleshooting.md](06-draft-troubleshooting.md)
**Agent:** Style guide reviewer v5 (`style-reviewer-v5.md`), with house-style.md v1.1
**Run:** Claude Projects, November 2026. Output copied verbatim; chat tables converted to Markdown.

---

## 1. Summary

**Total issues: 3 (7 places). High: 1. Medium: 2. Low: 0.**

**Top patterns**

- Passive voice in 5 places: 2 headings and 3 sentences (rule 2).
- "typed into" instead of "entered in" in 1 place (rule 8).
- A Troubleshooting section heading restates the symptom instead of stating a cause in 1 place (rule 7).

**What I couldn't check**

- Links. The input is plain text, so I can't tell whether "Update linked chart data," "Link a chart to Excel data," and "Fix a broken link to an Excel workbook" are links. Their wording follows rule 23.
- Images. The draft has none, so there was no alt text to check.

**Unresolved GAPs and CONFLICTs**

- GAP: how to tell whether a chart is linked to a workbook or uses the data grid. This is in "The chart's data was entered in the data grid."
- GAP: what happens to charts that aren't linked when you select Refresh All Charts. This is in "The chart's data was entered in the data grid."
- GAP: when the message appears, for example, when you select Refresh Data. This is in "The workbook was moved or deleted."
- GAP: Change Source steps. This is in "The workbook was moved or deleted."
- CONFLICTs: none.

## 2. Issues table

| # | Location | Original text | Issues | Rules | Suggested fix | Severity |
|---|---|---|---|---|---|---|
| 1 | Heading of section "Charts don't update automatically" | "Charts don't update automatically" | In a Troubleshooting article, section headings state causes. This heading restates the symptom. The cause, according to the body, is that refresh is manual. | 7 | "Charts need a manual refresh" | Medium |
| 2 | (a) "The workbook has unsaved changes," body. (b) Heading "The chart's data was entered in the data grid." (c) Same section, body. (d) Heading "The workbook was moved or deleted." (e) Same section, body. | Passive voice, 5 places: (a) "Unsaved changes aren't included." (b) "The chart's data was entered in the data grid" (c) "Charts with data typed into the Contoso Charts data grid can't be refreshed." (d) "The workbook was moved or deleted" (e) "If the linked workbook was moved or deleted, you see this message:" | Passive voice | 2 | (a) "Refresh doesn't include unsaved changes." (b) "The chart uses data from the data grid" (c) "You can't refresh charts with data typed into the Contoso Charts data grid." (d) "Someone moved or deleted the workbook" (e) "If someone moved or deleted the linked workbook, you see this message:" | High |
| 3 | "The chart's data was entered in the data grid," body | "Charts with data typed into the Contoso Charts data grid can't be refreshed." | "typed into" instead of "entered in" | 8 | Replace "typed into" with "entered in." Combined with fix 2(c), the sentence reads: "You can't refresh charts with data entered in the Contoso Charts data grid." | Medium |

## 3. Images

There are no images in the draft.

## 4. Questions for the writer

None.

---

Note how the reviewer applied house-style v1.1's new Troubleshooting exception both ways: it accepted the symptom title ("Charts don't update after editing Excel"), and it flagged a section heading that restated the symptom instead of naming a cause.
