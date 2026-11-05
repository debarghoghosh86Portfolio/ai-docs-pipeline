# Stage 7 output: Doc maintenance v2, after the Installation and Getting started release

**Input:**

- the publisher's files, patches, and publication record from [09-publisher.md](09-publisher.md)
- the open questions and six changes in [maintenance-inputs-install.md](../../maintenance-inputs-install.md)

The answer key is `maintenance-answer-key-install.md`.
**Agent:** Doc maintenance v2. **Run:** Claude Projects, November 2026. The output is summarized, with the change sets and verdicts kept as written.

## Drift summary (verbatim)

Three changes affect the published 4.4 docs. The 4.4.1 release (C2), which ships Feb 20, renames Color Palette to Colors and drops Windows 10 support. Nine support tickets (C4) suggest the Welcome pane statements mislead readers who updated from 4.3. The PM's answer to I-Q5 (C1) fills a gap in the Uninstall section. I-Q4 and P-Q1 are still unanswered, so Choose a chart type stays held.

**Change sets 3 · Tickets 9 · Critical 1 · High 4 · Medium 4 · No doc impact 4**

## Change sets

| CS-# | Cause | Articles | Route | Status |
|---|---|---|---|---|
| CS-1 | C2: 4.4.1 (rename to Colors, Windows 10 dropped, hidden-sheets fix) | System requirements; overview; **printed guide, figure 4**; Install; What's new (a new 4.4.1 entry, with the 4.4 entry left unchanged) | Intake | Hold until release (Feb 20); blocked on M-Q1 and M-Q4 |
| CS-2 | C4: 9 tickets, no Welcome pane after an update | Overview; Create a chart; Install > Update | Intake ("support's finding isn't confirmed behavior") | Blocked: M-Q2 |
| CS-3 | C1: I-Q5 answer (charts become static pictures, links removed) | Install > Uninstall | Drafter | Ready, with shared wording drafted |

No doc impact: C3 (reverted, not in any build), C5 (speculation), C6 (internal), and the hidden-sheets fix (no article describes the old behavior).

## Scored against the answer key

| Check | Result |
|---|---|
| Rename sweep finds the overview table, and mentions the figure | ✅ M-2, plus M-3 for the PDF figure. M-Q5 asks for a repository and PDF search beyond the inputs. |
| Windows 10 change keeps a 4.4 version note and covers the uninstall path | ✅ "Don't delete the 4.4 requirement." The Uninstall steps are flagged in the sweep and held until M-Q1. |
| I-Q5 answer routed to Install > Uninstall | ✅ CS-3, Ready, with shared wording |
| Support signal raised as a question, not a fact | ✅ CS-2 is Blocked on M-Q2 ("by design or a bug?") |
| C3, C5, and C6 under No doc impact | ✅ All three, plus the hidden-sheets fix |
| Hold until 4.4.1 for the C2 items | ✅ |

**Beyond the answer key:**

- **M-Q1:** the doc set has no policy for patch releases. The `product_version: "4.4+"` front matter becomes wrong on Feb 20.
- **M-Q4:** nobody has documented how to update from 4.4 to 4.4.1.
