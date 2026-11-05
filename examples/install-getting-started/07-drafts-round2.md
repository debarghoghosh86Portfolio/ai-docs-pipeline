# QA round 2 input: drafts after the SME round and the writer's fixes

These are the drafts sent to Doc QA round 2. Each one is the drafter's text from [03-drafts.md](03-drafts.md), with only the fixes listed in [06-sme-round-and-fixes.md](06-sme-round-and-fixes.md). New source blocks: Pack 1 [S4], Pack 2 [S6], Pack 3 [S3], and Pack 4 [S5] (SME answers).

## System requirements (New)

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

The installer is a single file, ContosoChartsSetup.exe. [S2] Download it from the Contoso Charts download page. If your IT team manages installations, it can get the file from the admin portal. [S4] No MSI package is available for Contoso Charts 4.4. [S2]

For more information, see Install Contoso Charts.
```

## Install Contoso Charts (Rewrite)

```markdown
# Install Contoso Charts

This article explains how to install, update, and uninstall Contoso Charts 4.4. [S0]

## Before you install

You need administrator rights on the computer. [S1] Without them, setup shows "You need administrator rights to install Contoso Charts." and stops. [S6]

Download ContosoChartsSetup.exe from the Contoso Charts download page. If your IT team manages installations, it can get the file from the admin portal. [S6]

Close PowerPoint before you run setup. If PowerPoint is open, setup shows "Close PowerPoint to continue." and waits. [S1]

For more information, see System requirements.

## Install

1. Close PowerPoint. [S2]
2. Double-click ContosoChartsSetup.exe. [S2]
3. On the Welcome page, select **Next**. [S2]
4. Read the license agreement, select **I accept the agreement**, and then select **Next**. [S2]
5. Keep the default install location, or select **Browse** to choose another folder. Then select **Next**. [S2]
6. Select **Install**. A progress bar shows the installation status. [S2]
7. Select **Finish**. [S2]
8. Open PowerPoint. The **Contoso Charts** tab appears on the ribbon. The first time you open PowerPoint, the Welcome pane opens on the right. [S2] For more information, see Contoso Charts overview.

To create your first chart, see Create a chart.

## Update

To update from Contoso Charts 4.3, run the Contoso Charts 4.4 setup file, ContosoChartsSetup.exe. [S3] [S2] Setup upgrades Contoso Charts in place. [S3] Close PowerPoint first. If PowerPoint is open, setup shows "Close PowerPoint to continue." and waits. [S6] Setup shows the same pages as a new installation and keeps the install location. [S6]

You don't need to uninstall Contoso Charts 4.3 first. [S3] Existing linked charts keep their links after the update. [S3]

To update from a version earlier than Contoso Charts 4.3, uninstall it first, and then install Contoso Charts 4.4. [S6]

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

## Contoso Charts overview (Update: changed passages only)

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

The **Contoso Charts** tab organizes its buttons into four groups. [S1] **Link to Excel** and the Welcome pane are new in Contoso Charts 4.4. [S3]

| Group | Buttons |
|---|---|
| **Create** | **New Chart**, **Edit Data** [S1] |
| **Data** | **Link to Excel**, **Refresh Data**, **Refresh All Charts**, **Change Data Source** [S1] |
| **Format** | **Chart Styles**, **Color Palette** [S1] |
| **Export** | **Export to PDF** [S1] |

To add a chart, see Create a chart.

**Edit Data** opens the data grid. [S1] For more information, see Enter data in the data grid.

For more information about the **Data** group, see Link a chart to Excel data, Update linked chart data, and Change a chart's data source.

For more information about the **Export** group, see Export charts to PDF.

<!-- CHANGE 4. NEW SECTION. Add it directly after the "Contoso Charts tab"
     section. -->

## Welcome pane

The Welcome pane opens on the right the first time you open PowerPoint after you install Contoso Charts. [S2] It opens only that first time, and you can't reopen it in Contoso Charts 4.4. [S2] [S3]

The **Create your first chart** button on the Welcome pane does the same thing as **New Chart** in the **Create** group. [S1] [S2]
```

## Create a chart (Update: changed passages only)

```markdown
<!-- UPDATE: Create a chart (TOC: Create charts; guide: Getting started) -->

<!-- PASSAGE 0
     Goes under: the title. Replaces: the existing intro sentence. -->

This article explains how to create a chart in Contoso Charts 4.4. [S0] For an overview of the Contoso Charts tab, see Contoso Charts overview.

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
     Replaces: the existing section body. -->

## Use the Welcome pane

The first time you open PowerPoint after you install Contoso Charts, the Welcome pane opens on the right. [S2 (Pack 3)] It opens only the first time, and you can't reopen it in Contoso Charts 4.4. [S2 (Pack 3)] [S5]

In the Welcome pane, you can select **Create your first chart** instead of **New Chart**. Both buttons do the same thing. [S1] [S2 (Pack 3)]

<!-- PASSAGE 3
     Goes under: "## Add your data". Replaces: the existing section body. -->

## Add your data

To replace the sample data, select the chart, and then select **Edit Data**. The data grid opens. [S2] For more information, see Enter data in the data grid.

To use data from an Excel workbook instead, see Link a chart to Excel data.
```

## Link a chart to Excel data (Update: changed passages only)

```markdown
<!-- UPDATE 1 — Intro. Replaces the existing intro sentence, directly under the title. -->

When you link a chart to a range in an Excel workbook, the chart shows the data from that range. [S3] **Link to Excel** is new in Contoso Charts 4.4. [S0] [S5]

<!-- UPDATE 2 — "## Link a chart". Replaces all of the 2024 "Select Data > From Excel" steps under this heading. Delete the old UI path wherever else it appears in the article. -->

## Link a chart

1. Select the chart. [S3]
2. On the **Contoso Charts** tab, in the **Data** group, select **Link to Excel**. The **Link to Excel** dialog box opens. [S3]
3. In the **Link to Excel** dialog box, select **Browse**, and then select the workbook. Only Excel workbooks (.xlsx) are supported. [S5]
4. Select the sheet, and then enter the range in the **Range** box, for example A1:D12. [S5]
5. Select **OK**. The chart shows the data from that range. [S3]

<!-- UPDATE 3 — "## After you link". Add the two new sentences at the start of this section. KEEP the existing sentence that linked charts don't update automatically, directly after them. Then add the three link sentences. If the article doesn't have this heading yet, add it after "Link a chart." -->

## After you link

After you link a chart, **Edit Data** is unavailable for that chart. [S4] To change the data, edit it in Excel, and then refresh the chart. [S4]

<!-- KEEP: existing sentence that linked charts don't update automatically. -->

For more information, see Update linked chart data.

For help with a link that stops working, see Fix a broken link to an Excel workbook.

If a chart doesn't change after you edit the workbook, see Charts don't update after editing Excel.
```

## What's new in Contoso Charts (Update: one bullet in the 4.4 entry)

```markdown
<!-- UPDATE: What's new in Contoso Charts. Add this bullet to the existing "Contoso Charts 4.4" entry, after the existing bullets. Don't change the 4.3 entry. -->

- Contoso Charts 4.4 has a new installer, ContosoChartsSetup.exe. It requires 64-bit Windows 10 or Windows 11, PowerPoint 2016 or later, and administrator rights to install. PowerPoint 2013 isn't supported. [S1] [S2] For more information, see System requirements.
```

