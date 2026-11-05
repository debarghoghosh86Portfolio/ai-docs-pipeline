# Answer key: publishing the Contoso Charts 4.3 docs

Check the Publishing agent's output against this list AFTER you run it.

## Expected gate results

| Article | Expected result | Why |
|---|---|---|
| Update linked chart data | **Publish** (full file) | QA Ready. Only source tags and one evidence note "(R3, Done, 4.3)" to remove. |
| Charts don't update after editing Excel | **Back to writer** | QA-3 claimed fixed, but the text still says "select **Refresh All**." (QA-2 was applied.) |
| Link a chart to Excel data | **Hold** | QA verdict Missing. |
| Error messages | **Hold** | QA verdict Blocked. |
| Keyboard shortcuts | **Back to writer** | QA-7 was applied, but the row contains "Mac shortcut TBD (I-Q6)", an internal reference. Removing it would be editing. |
| What's new in Contoso Charts | **Publish** (patch) | All three fixes applied. Remove "[S3]", "[S1] [S2]", and "(R3, Done, 4.3)". |
| CS-2 (Ctrl+Shift+R) | **Hold** | Hold until release. |
| CS-3 (Windows only) | **Back to Drafter** | Ready, but no drafted text. (The rewrite already includes "Refresh isn't available on Mac," so a good answer may say CS-3 is already covered in that article but still needs drafting for the others.) |

So: Publishing 2 (1 full file, 1 patch) · Held back or returned 6 · Redirects 0.

## Traps

| # | Trap | Correct handling |
|---|---|---|
| 1 | A fix claimed as applied that isn't (QA-3) | Verify against the text; send back |
| 2 | Internal reference "TBD (I-Q6)" in a Ready-after-fixes draft | Don't publish; don't delete it yourself |
| 3 | Evidence note "(R3, Done, 4.3)" in two drafts | Remove it (allowed) |
| 4 | "Ready" change set with no draft (CS-3) | Back to Drafter, not published |
| 5 | Links to articles not in this release (Error messages, Change a chart's data source, Fix a broken link, Link a chart to Excel data) | Still link them. They exist on the live site. Not a problem. |
| 6 | No retire or rename | No redirects. Don't invent any. |
| 7 | Keyboard shortcuts and What's new are Updates | Patches, not full files |
| 8 | Release risk: the new "Update linked chart data" goes live while the old "Charts don't update after editing Excel" (live version says charts update every 5 minutes) is held back | Flag it. Recommend fixing QA-3 quickly and publishing both together, or holding the main article. The docs lead decides. |
| 9 | Release risk: What's new links to Keyboard shortcuts, which won't show Ctrl+Alt+R until its row is fixed | Flag it (minor). |

## Front matter checks (Update linked chart data)

- title: "Update linked chart data"
- slug: "/work-with-data/update-linked-chart-data" (from the slug map, unchanged)
- doc_type: "task"; toc_section: "Work with data"
- product_version: "4.3+"
- last_updated: "2026-11-20"
- description: 160 characters or fewer, from the first sentence, no new facts
- keywords: 3–6 terms that appear in the article

## Scoring

| Check | Pass? |
|---|---|
| Update linked chart data published, tags and evidence note removed, no other wording changed | |
| QA-3 caught as claimed but not applied | |
| "TBD (I-Q6)" caught; Keyboard shortcuts not published | |
| What's new published as a patch | |
| Error messages and Link a chart held | |
| CS-2 held; CS-3 back to Drafter | |
| Links built from the slug map, including articles outside this release | |
| No redirects invented | |
| Release risk flagged for the stale troubleshooting article | |
| Front matter matches the schema | |
| PR description and publication record included | |
