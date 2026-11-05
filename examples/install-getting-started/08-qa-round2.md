# Stage 5 output: Doc QA v1, round 2

**Input:** the same QA chat as round 1. It received the new SME source blocks, the docs lead decisions, and the revised drafts in [07-drafts-round2.md](07-drafts-round2.md).
**Agent:** Doc QA v1, with v1.2 rule 7 applied as instructed (the project file is still v1.1).
**Run:** Claude Projects, November 2026. The summary and the new issues are copied verbatim.

---

## 1. Release summary

The revised drafts close every round 1 issue that the writer could fix. The new source blocks answer all of the open [GAP] markers, and every quoted UI and setup message matches the packs character for character. No draft is blocked. Two drafts need small writer or docs lead fixes: Create a chart has one unbolded UI label, and the new What's new bullet has source tags with no pack and a link that isn't in the link map. Choose a chart type stays held for intake, as the docs lead accepted.

**Ready: 4 · Ready after fixes: 2 · Blocked: 0 · Missing: 1**

## 2. Doc status

| Draft | Verdict |
|---|---|
| System requirements (New) | Ready |
| Install Contoso Charts (Rewrite) | Ready (8 steps; overview link in step 8) |
| Contoso Charts overview (Update) | Ready |
| Create a chart (Update) | Ready after fixes (QA-14) |
| Link a chart to Excel data (Update) | Ready |
| What's new in Contoso Charts (Update, docs lead, P-Q3) | Ready after fixes (QA-15, QA-16) |
| Choose a chart type (Update, row 6) | Missing (P-Q1) |

## 3. Round 1 issues

QA-3, QA-4, QA-6, QA-7, QA-8, QA-9, QA-10, and QA-13 are **fixed**. QA-5 and QA-12 are **closed** by docs lead decisions. QA-11 is **moot**. QA-2 is an **accepted risk**. QA-1 is **still open** (held for intake).

## 4. New issues

| QA-# | Draft | Check | Problem | Evidence (quote) | Fix | Needs SME? |
|---|---|---|---|---|---|---|
| QA-14 | Create a chart | 4 Terminology | The tab name isn't bold in the new intro. Every other draft, and step 1 of this draft, bolds it. | "For an overview of the Contoso Charts tab, see Contoso Charts overview." | Change it to "the **Contoso Charts** tab." | No |
| QA-15 | What's new in Contoso Charts | 6 Unsourced facts | The tags don't name a pack, and this article has no pack of its own. Packs 2, 3, and 4 also have [S1] and [S2]. The facts match Pack 1 [S1] and [S2]. | "PowerPoint 2013 isn't supported. [S1] [S2]" | Change the tags to "[S1 (Pack 1)] [S2 (Pack 1)]." | No |
| QA-16 | What's new in Contoso Charts | 3c Links | The link to System requirements isn't in the link map. Its text matches the destination title. | "For more information, see System requirements." | Docs lead adds the row "What's new in Contoso Charts → System requirements" to the link map. | No (docs lead) |

## 5. New questions

- **QA-Q6 (docs lead):** Does the Install ruling ("a wizard page is one step") also apply to the Choose a Chart Type and Link to Excel dialog boxes? Create a chart splits its dialog into steps 2 and 3, and Link a chart to Excel data splits its dialog into steps 3 to 5. "This split was already in round 1's Create a chart, and I missed it."
- **QA-Q7 (docs lead):** Does the existing What's new 4.4 entry already mention Link to Excel and the Welcome pane? The overview and Link a chart to Excel data drafts now say both are new in 4.4.

It also kept one SME question open: **I-Q5** "now matters more." Install tells users of versions earlier than 4.3 to uninstall first, but nothing says what happens to their linked charts.

---

## Scored

| Check | Result |
|---|---|
| Every round 1 fix verified against the text, not just trusted | ✅ All 13 tracked |
| Every quoted message checked character for character | ✅ |
| Problems found after the fixes | ✅ 3 small issues, and 2 questions nobody planted |

**Beyond expectations:**

- **QA-Q7** found a real gap. The finished What's new 4.4 entry never announced Link to Excel or the Welcome pane, even though two drafts now say both are new in 4.4.
- **QA-Q6** admitted a miss from round 1 and turned it into a rule question, instead of quietly changing a verdict.

**Docs lead decisions after round 2:**

- **QA-14 and QA-15:** fixed by the writer.
- **QA-16:** the link map row is added.
- **QA-Q6:** the ruling covers wizard pages only. A dialog box with separate fields keeps one step per field.
- **QA-Q7:** a What's new bullet for Link to Excel and the Welcome pane is added. That bullet hasn't been through QA, which is the publisher's first test.
- **I-Q5:** stays open, and isn't blocking.
