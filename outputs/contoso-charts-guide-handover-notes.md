# Handover notes: Contoso Charts User Guide (4.4)

These notes are internal and don't go to the customer. They go with `contoso-charts-user-guide.pdf`.

## Where each chapter comes from

| Chapter | Built from | Pipeline run |
|---|---|---|
| 1. What's new | 4.3: the published patch. 4.4: approved release notes, plus two bullets the docs lead added (installer and requirements per P-Q3; Link to Excel and the Welcome pane per QA-Q7). | Refresh run, plus the full-guide run |
| 2. Installation | The System requirements and Install Contoso Charts drafts, after QA round 2 | **Full-guide run** (intake v4 → planner v3 → drafter v7 → reviewer v5 → QA ×2) |
| 3. Getting started | The drafts for Contoso Charts overview, Create a chart, and Link a chart to Excel data, after QA round 2. Export to PDF comes from the earlier Export source pack, with no change per the plan. | **Full-guide run** |
| 4–7 | Refresh charts, Data sources, Troubleshooting, Reference | Refresh run and maintenance |

**Every fact in chapters 2 and 3 now traces to a source block.** See `examples/install-getting-started/`. The made-up details in the previous version are gone, and some were wrong:

| Earlier guess | Pipeline fact |
|---|---|
| Insert Chart | **New Chart** |
| Data Grid | **Edit Data** |
| Colors | **Color Palette** |
| "Select Close" at the end of setup | **Finish** |
| Linking through Change Data Source | **Link to Excel** |

## Figures

There are 12 drawn mockups. The product is fictional, so these aren't screenshots. Every label in a figure matches a source:

- **Ribbon:** the UI spec R5
- **License page and installer:** the passed test script R4
- **Choose a Chart Type and Link to Excel:** the feature spec R7 and the SME answer for I-Q9
- **Welcome pane:** R4 and R6 (only the title and the **Create your first chart** button)

The sample file path and range ("Q3-sales.xlsx," "A1:D12") are example values.

## Still open (left out of the guide, so it makes no claim about them)

- **P-Q1:** the Area entry in Choose a chart type. That article is held. The guide doesn't describe the chart types.
- **I-Q5:** what happens to linked charts after you uninstall
- **I-Q4:** whether to keep content for 4.3 and earlier installs
- **The Chart Styles and Color Palette buttons:** what they do. Nobody asked.
- **I-Q7, I-Q8, I-Q10, P-Q4:** SME confirmation that finished articles are accurate for 4.4
- **W-Q1:** retitling two web articles that break house-style rule 7
- **Maintenance:** CS-1 (4.4.1: Color Palette → Colors, Windows 10 dropped) is held until Feb 20 and will change figure 4 and chapter 2. CS-3 (what happens after uninstall) is Ready.
