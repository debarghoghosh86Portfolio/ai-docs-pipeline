# Maintenance inputs: after the Installation and Getting started release

Test material for Doc maintenance v2. Paste the publisher's output (published files, patches, and publication record) plus the open questions and change material below. The answer key is `maintenance-answer-key-install.md`.

---

=== PART 2: OPEN QUESTIONS FROM EARLIER STAGES ===
I-Q4: Should the Installation chapter keep any content for 4.3 or earlier?
I-Q5: After users uninstall Contoso Charts, what happens to charts in existing presentations?
P-Q1: Source material for the Area chart type (Choose a chart type is held).

=== PART 3: CHANGE MATERIAL SINCE THE RELEASE (2027-02-10) ===

[C1] SME answer (email from the PM) — Feb 12
- I-Q5: "After uninstall, charts stay in the presentation as static pictures.
  Links to Excel are removed. If you reinstall, you have to relink them."

[C2] Contoso Charts 4.4.1 release notes (approved, ships Feb 20)
- "The Color Palette button is now named Colors."
- "Windows 10 is no longer supported. Contoso Charts 4.4.1 requires
  Windows 11, 64-bit."
- "Fixed: Link to Excel didn't show hidden sheets."

[C3] Pull request #1102 — merged Feb 5 — "Rename Choose a Chart Type dialog title"
- Changes the dialog box title from "Choose a Chart Type" to "Insert Chart".
- Status: reverted Feb 6 ("Insert Chart is the old button name; it confuses
  users"). Not in any build.

[C4] Support tickets — Jan 25 to Feb 10
- 9 tickets: "Installed Contoso Charts but the Welcome pane never appeared."
  Support's finding: in all 9 cases, the user had updated from 4.3. None of
  them was a new installation.

[C5] Slack, #contoso-charts-dev — Feb 8
- PM: "Maybe a per-user installer in 4.6 if IT asks again."

[C6] Pull request #1110 — merged Feb 9 — "Move installer logging to a
  background thread." Internal change. No change to the UI or behavior.
