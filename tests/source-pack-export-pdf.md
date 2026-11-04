Doc type: Task
Audience: Contoso Charts users who build presentations in PowerPoint

[S1] Product spec excerpt — Feature: Export to PDF (Contoso Charts 4.2)
- Users can export one or more charts from a presentation to a single PDF file.
- Entry point: Contoso Charts tab on the ribbon > Export group > Export to PDF.
- Opens the "Export Charts to PDF" dialog box. Options:
  - "Charts to export": All charts in presentation / Selected charts
  - "Page size": A4 or Letter. Default: Letter.
  - "Include chart titles" check box. Default: on.
- Maximum charts per export: 50.
- Requires PowerPoint 2016 or later.
- Internal: code name "Bluebird." Phase 2 will add PNG export.

[S2] Jira ticket CCH-1182 (status: Done)
Export to PDF is unavailable (grayed out) if the presentation has no charts.
Tooltip text: "Add a chart to enable export."
Also: export fails silently if the file path is longer than 255 characters.
Fixed in 4.2.1, not in 4.2.

[S3] SME call notes — Priya (QA lead)
- "In testing, anything over 20 charts timed out. We set the limit to 20 in
  the final build."
- "After you select Export in the dialog, a Save As dialog opens. You pick the
  location and file name, then Save. A progress bar shows, and then the PDF
  opens automatically if 'Open after export' is checked. That check box is in
  the Export dialog too. It's off by default."
- "Exported charts are static images. You can't edit them in the PDF."
- "Honestly, the UI team hated this dialog. We argued about it for weeks."
