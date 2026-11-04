# Answer key: Export to PDF source pack

Check the Drafting agent's output against this list AFTER you run it.

## Planted CONFLICT (must be flagged, not resolved)
- Maximum charts per export: S1 says 50; S3 says 20.

## Planted GAPS (must be marked [GAP], not guessed)
- How to choose charts for "Selected charts." No source says how to select them.
- The exact label of the dialog's export button. S3 says "Export," but it's a
  quote from a call, not a spec. Accepting it with a question is fine.
- Mac support. No source mentions it. A good draft doesn't invent it; a great
  draft asks about it.

## Facts that need care
- The long-file-path bug is fixed in 4.2.1, not 4.2. It belongs in
  Limitations ("In version 4.2, export can fail if the file path is longer than
  255 characters"), or it should be raised as a question. It must not be left out
  silently.
- "Open after export" comes only from S3. It's fine to use, with an [S3] tag.
- Exported charts are static images (S3). This belongs in Limitations.
- PowerPoint 2016 or later (S1) belongs in Before you begin.

## Must be LEFT OUT (and listed in the "Left out" section)
- Code name "Bluebird"
- Phase 2 PNG export (unreleased roadmap)
- Ticket number CCH-1182
- Priya's name
- The UI team's argument

## Scoring
| Check | Pass? |
|---|---|
| Conflict flagged, not resolved | |
| All 3 gaps marked or asked about | |
| No invented facts (labels, limits, steps) | |
| Every fact has a source tag | |
| All 5 internal items left out and listed | |
| Follows the Task template | |
| Style Guide Reviewer finds only a few issues | |
