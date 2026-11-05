# Stage 3 output: Doc drafter v7, five drafts for Installation and Getting started

**Input:** Briefs 1–5 from [02-doc-plan.md](02-doc-plan.md) (approved), the matching source packs from [01-intake-output.md](01-intake-output.md), and every open I-Q and P-Q question.
**Agent:** Doc drafter v7 (`doc-drafter-v7.md`), with house-style.md v1.2
**Run:** Claude Projects, November 2026. Five runs, one chat per brief. The drafts are copied verbatim. The SME questions and "Left out" notes are summarized after each draft.

The `[S#]` tags tie every sentence to a block in the draft's source pack. `[GAP]` markers point to questions that are already open.

---

## Brief 1: System requirements (New)

```markdown
# System requirements

This article lists what you need to install Contoso Charts 4.4. [S0]

## Requirements

| Requirement | Details |
|---|---|
| Operating system | Windows 10 or Windows 11, 64-bit. [S1] |
| PowerPoint version | PowerPoint 2016 or later. Contoso Charts 4.4 doesn't support PowerPoint 2013. [S1] [S3] |
| Permissions | Installing Contoso Charts 4.4 requires administrator rights on the computer. [S1] |

## Installer file

The installer is a single file, ContosoChartsSetup.exe. [S2] [GAP: where users get ContosoChartsSetup.exe — see I-Q1] No MSI package is available for Contoso Charts 4.4. [S2]

For more information, see Install Contoso Charts.
```

**New questions:**

- D-Q1: Are there any other requirements, such as disk space or memory?
- D-Q2: Does "2016 or later" include PowerPoint for Microsoft 365? Is 32-bit PowerPoint supported?

## Brief 2: Install Contoso Charts (Rewrite)

```markdown
# Install Contoso Charts

This article explains how to install, update, and uninstall Contoso Charts 4.4. [S0]

## Before you install

You need administrator rights on the computer. [S1] [GAP: what happens if you run setup without administrator rights — see I-Q2]

Close PowerPoint before you run setup. If PowerPoint is open, setup shows "Close PowerPoint to continue." and waits. [S1]

For more information, see System requirements.

## Install

1. Close PowerPoint. [S2]
2. Double-click ContosoChartsSetup.exe. [GAP: where to get ContosoChartsSetup.exe — see I-Q1] [S2]
3. On the **Welcome** page, select **Next**. [S2]
4. Read the license agreement, select **I accept the agreement**, and then select **Next**. [S2]
5. Keep the default install location, or select **Browse** to choose another folder. Then select **Next**. [S2]
6. Select **Install**. A progress bar shows the installation status. [S2]
7. Select **Finish**. [S2]
8. Open PowerPoint. The **Contoso Charts** tab appears on the ribbon. The first time you open PowerPoint, the **Welcome** pane opens on the right. [S2] For more information, see Contoso Charts overview.

To create your first chart, see Create a chart.

## Update

To update from Contoso Charts 4.3, run the Contoso Charts 4.4 setup file, ContosoChartsSetup.exe. [S3] [S2] Setup upgrades Contoso Charts in place. [S3] [GAP: whether you must close PowerPoint before you update, and whether versions earlier than Contoso Charts 4.3 can update in place — see I-Q3] [GAP: whether the update uses the same setup wizard pages as a new installation]

You don't need to uninstall Contoso Charts 4.3 first. [S3] Existing linked charts keep their links after the update. [S3]

## Uninstall

On Windows 11:

1. Open **Settings**. [S4]
2. Select **Apps**. [S4]
3. Select **Installed apps**. [S4]
4. For **Contoso Charts**, select **More (...)**. [S4]
5. Select **Uninstall**. [S4]

On Windows 10:

1. Open **Control Panel**. [S4]
2. Select **Programs**. [S4]
3. Select **Programs and Features**. [S4]
4. Select **Contoso Charts**. [S4]
5. Select **Uninstall**. [S4]
```

**New questions:**

- D-Q1: Does an update show the same wizard pages, and does it keep the install location?
- D-Q2: Do update and uninstall need administrator rights?
- D-Q3: Does uninstall show a confirmation prompt, does the tab disappear, and must PowerPoint be closed?
- D-Q4: What's the default install location?

**Left out:** the requirements are left out and linked instead, as the brief says. The "Close PowerPoint to continue." message isn't repeated in the steps. Nothing is added to Error messages or Troubleshooting, because P-Q5 is pending.

## Brief 3: Contoso Charts overview (Update, changed passages only)

```markdown
<!-- UPDATE: Contoso Charts overview (Getting started, first article).
     Draft only. Leave all other text as it is. -->

<!-- CHANGE 1. Throughout the article, including the kept product
     description: replace every "Insert Chart" with **New Chart**. [S1] -->

<!-- CHANGE 2. Remove the sentence "Select Insert Chart to add a chart."
     from wherever it appears. Its replacement link ("To add a chart, see
     Create a chart.") is in the "Contoso Charts tab" section that follows. -->

<!-- SECTION "What Contoso Charts does": keep the existing content.
     Apply only Change 1 and Change 2. -->

<!-- CHANGE 3. Replace the body of the existing "Contoso Charts tab" section
     with the text that follows. The table keeps the four group names. -->

## Contoso Charts tab

In Contoso Charts 4.4 and later, the **Contoso Charts** tab organizes its buttons into four groups. [S0] [S1]

| Group | Buttons |
|---|---|
| **Create** | **New Chart**, **Edit Data** [S1] |
| **Data** | **Link to Excel**, **Refresh Data**, **Refresh All Charts**, **Change Data Source** [S1] |
| **Format** | **Chart Styles**, **Color Palette** [S1] |
| **Export** | **Export to PDF** [S1] |

To add a chart, see [Create a chart](#).

**Edit Data** opens the data grid. [S1] For more information, see [Enter data in the data grid](#).

For more information about the **Data** group, see [Link a chart to Excel data](#), [Update linked chart data](#), and [Change a chart's data source](#).

For more information about the **Export** group, see [Export charts to PDF](#).

<!-- CHANGE 4. NEW SECTION. Add it directly after the "Contoso Charts tab"
     section. -->

## Welcome pane

In Contoso Charts 4.4 and later, the Welcome pane opens on the right the first time you open PowerPoint after you install Contoso Charts. [S0] [S2] It opens only that first time. [S2] [GAP: whether you can reopen the Welcome pane after you close it — see I-Q6]

The **Create your first chart** button on the Welcome pane does the same thing as **New Chart** in the **Create** group. [S1] [S2] [GAP: what else the Welcome pane shows]
```

**New question:** D-Q1: What else does the Welcome pane show, and how do you close it?

**Left out:** descriptions of the Data, Format, and Export buttons, because "no source describes them." The product description is kept unchanged, and the drafter didn't invent it.

## Brief 4: Create a chart (Update, changed passages only)

```markdown
<!-- UPDATE: Create a chart (TOC: Create charts; guide: Getting started) -->

<!-- PASSAGE 1
     Goes under: "## Create a chart" (second heading in the brief's outline)
     Replaces: the existing procedure, which uses "Insert Chart" and lists
     four chart types. -->

## Create a chart

1. On the **Contoso Charts** tab, in the **Create** group, select **New Chart**. The **Choose a Chart Type** dialog box opens. [S1]
2. In the **Choose a Chart Type** dialog box, select **Column**, **Bar**, **Line**, **Pie**, or **Area**. [S1]
3. Select **Insert**. The chart appears on the slide with sample data. [S1]

For more information, see Choose a chart type.

<!-- PASSAGE 2
     Goes under: "## Use the Welcome pane" (third heading in the brief's outline)
     Replaces: the existing section body, if it says "Insert Chart." See D-Q1. -->

## Use the Welcome pane

The first time you open PowerPoint after you install Contoso Charts, the Welcome pane opens on the right. [S2 (Pack 3)] It opens only the first time. [S2 (Pack 3)] [GAP: whether you can reopen the Welcome pane after you close it — see I-Q6]

In the Welcome pane, you can select **Create your first chart** instead of **New Chart**. Both buttons do the same thing. [S1] [S2 (Pack 3)]

<!-- NOT DRAFTED (no change in the brief): the intro sentence and "## Add your data."
     If either one says "Insert Chart," change it to "New Chart." See D-Q1. -->
```

**New question:** D-Q1 (docs lead): The current article wasn't provided. Does the intro or "Add your data" also mention Insert Chart?

## Brief 5: Link a chart to Excel data (Update, changed passages only)

```markdown
<!-- UPDATE 1 — Intro. Replaces the existing intro sentence, directly under the title. -->

When you link a chart to a range in an Excel workbook, the chart shows the data from that range. [S3] **Link to Excel** is available in Contoso Charts 4.4 and later. [S0]

<!-- UPDATE 2 — "## Link a chart". Replaces all of the 2024 "Select Data > From Excel" steps under this heading. Delete the old UI path wherever else it appears in the article. -->

## Link a chart

1. Select the chart. [S3]
2. On the **Contoso Charts** tab, in the **Data** group, select **Link to Excel**. The **Link to Excel** dialog box opens. [S3]
3. In the **Link to Excel** dialog box, browse to the workbook (.xlsx) and select the range. [GAP: how to select the range, and whether formats other than .xlsx are supported — see I-Q9] [S3]
4. Select **OK**. The chart shows the data from that range. [S3]

<!-- UPDATE 3 — "## After you link". Add the two new sentences at the start of this section. KEEP the existing sentence that linked charts don't update automatically, directly after them. Then add the three link sentences. If the article doesn't have this heading yet, add it after "Link a chart." -->

## After you link

After you link a chart, **Edit Data** is unavailable for that chart. [S4] To change the data, edit it in Excel, and then refresh the chart. [S4]

<!-- KEEP: existing sentence that linked charts don't update automatically. -->

For more information, see Update linked chart data.

For help with a link that stops working, see Fix a broken link to an Excel workbook.

If a chart doesn't change after you edit the workbook, see Charts don't update after editing Excel.
```

**New questions:**

- D-Q1: Can you unlink a chart?
- D-Q2: What message appears if linking fails?
- D-Q3: Is there a range size limit?
- D-Q4: Does linking work for all five chart types, and is it unavailable when no chart is selected?

---

## Scored against the answer key

| Check | Result |
|---|---|
| Brief titles and headings, in order | ✅ All five |
| Short headings (v1.2, rule 7) | ✅ The longest heading is "Refresh all linked charts…" (none in these drafts). Every new heading is 1–4 words. |
| Every sentence tagged, with no evidence notes | ✅ |
| No invented facts | ✅ **None in five drafts.** The setup file location, the Welcome pane reopen, the range selection, and the button behavior are all GAPs or left out. |
| GAPs point to existing questions | ✅ I-Q1, I-Q2, I-Q3, I-Q6, I-Q9 |
| Chart Styles and Color Palette | ⚠️ Correctly left undescribed, but no draft asks what they do. Intake missed this too. |
| Brief 3's kept product description | ✅ It's left as "keep existing content." Nothing is invented. |

**Limit this exposes:** Briefs 3–5 are Updates, so the drafter wrote only the changed passages and kept placement notes for the writer. That's the right behaviour for a live site, but the drafter never saw the current articles. A guide needs whole chapters, so assembling the guide means merging these passages into the live text. That job falls to the publisher or the writer.
