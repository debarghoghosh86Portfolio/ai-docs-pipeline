# AI Documentation Pipeline: Seven Agents from Raw Material to Published, Maintained Docs

**Author:** Debargho Ghosh, Technical Writer (16 years, internal and external documentation)
**Status:** All seven stages of an end-to-end AI documentation pipeline are
built and tested: Intake (v4), Planning (v3), Drafting (Doc drafter v7), Review
(Style guide reviewer v5), QA (v1), Publishing (v1), and Maintenance (v2).
Planner, drafter, reviewer, and QA share one house style (v1.2).

**Quick links:** [one-page case study](case-study/case-study-ai-docs-pipeline.pdf) ·
[full report](case-study/ai-docs-pipeline-report.pdf) ·
[the user guide the pipeline produced](outputs/contoso-charts-user-guide.pdf) ·
[example runs with real outputs](examples/)

## Summary

I designed, tested, and connected seven AI agents that cover the whole
documentation lifecycle:

- **Doc intake:** reads messy raw material (Slack threads, meeting notes,
  tickets, pull requests, support emails), decides which docs need to be
  written or fixed, and produces a clean, evidence-backed source pack for each.
  It applies the latest decision, drops anything that isn't shipping, strips
  confidential details, and starts one shared SME question list.
- **Doc planner:** acts as lead writer and information architect. It checks
  intake's list against the existing doc set, chooses New, Update, Rewrite,
  Merge, or Retire for each doc, finds stale articles intake couldn't see,
  places each doc in the table of contents, and writes a drafting brief with an
  outline mapped to the source facts.
- **Doc drafter:** turns source material and the planner's brief into a
  first draft, using Task, Concept, Reference, or Troubleshooting templates. It cites a source for every fact, marks missing information as
  `[GAP]`, flags disagreements between sources as `[CONFLICT]`, and leaves out
  internal details such as code names and ticket numbers.
- **Style guide reviewer:** checks a draft against the house style and returns a
  prioritized issues table, an accessibility check for every image, and
  questions for the writer. It never rewrites the document or guesses at facts.
- **Doc QA:** checks the whole release before publishing: every planned doc has
  a draft, links match the link map and use exact titles, terms and facts are
  consistent across articles, and quoted messages match the source. It gives
  each draft a release verdict (Ready, Ready after fixes, Blocked, or Missing)
  and one combined list of questions blocking release.
- **Doc publisher:** the last gate before readers. It publishes only what's
  ready, verifies that claimed fixes are really in the text, removes internal
  markers without changing a word, adds front matter, turns link text into
  links, and prepares Markdown files, patches, a pull request description, and
  a publication record for maintenance.
- **Doc maintenance:** after publishing, compares new changes (release notes,
  pull requests, SME answers, support tickets) against the published docs and
  finds "drift": sentences that are now wrong, incomplete, or confusing. It
  groups the fixes into change sets with one shared wording, routes each set
  back into the pipeline, and holds changes until their release ships.

The planner, drafter, reviewer, and QA agent follow one rules file,
**house-style.md**. A rule changed once applies to all four.

**Result:** raw, contradictory material went in, and a draft came out that the
reviewer found **0 issues** in, compared with **27** on a legacy hand-written
help page. No agent invented a fact, every planted trap was caught, and the SME
gets one combined question list (I-Q# from intake, P-Q# from the planner, D-Q#
from the drafter). The planner caught all eight planted structure traps,
including a duplicate article and a stale troubleshooting page intake never saw.
The QA agent caught all ten planted release defects with no false alarms, plus
a missing link I hadn't planted. The maintenance agent found every planted
drift, including a rename in five articles, and left history (earlier release
notes) untouched. The publisher held back every item that wasn't ready,
including a fix a writer claimed but hadn't made, and published the rest with
no wording changes.

**See for yourself:** [`examples/refresh-from-excel/`](examples/refresh-from-excel/)
has one full run with the agents' real outputs: the raw input, intake's source
packs, the doc plan, drafts with `[S#]` tags, the reviewer's issues tables, and
QA's release verdicts.

## The pipeline

```
Raw material ──► Doc intake ──► doc impact + source packs ──► (writer confirms scope)
                                                                      │
Existing docs inventory ──► Doc planner ◄─────────────────────────────┘
                                │
                                ▼
                 doc plan + drafting briefs ──► (docs lead approves plan)
                                                          │
          ┌───────────────────────────────────────────────┘
          ▼
     Doc drafter ──► draft with [S#], [GAP], [CONFLICT] ──► Style guide reviewer ──► review
                                                                              │
          all drafts + plan + link map + source pack ◄────────────────────────┘
                                │
                                ▼
                            Doc QA ──► release verdicts + blocking questions ──► (docs lead signs off)
                                │
                                ▼
                         Doc publisher ──► files + patches + PR + publication record ──► (docs lead approves merge)
                                │
                                ▼
New changes + published docs ──► Doc maintenance ──► change sets (Ready / Hold / Blocked)
                                                          │
                     routed back to Intake, Planner, or Drafter ◄──┘   (the loop)

Shared by the planner, drafter, reviewer, and QA: house-style.md (one set of rules)
```

All seven stages of the lifecycle are built:

**Intake** → **Planning** → **Drafting** → **Review** → **QA** → **Publishing** → **Maintenance**

Six human checkpoints keep a writer in charge: confirm scope, approve the plan,
edit the draft, sign off the release, approve the merge, and approve
maintenance tickets.

## Part 1: Style guide reviewer

### How it's built

The agent is a set of instructions (a system prompt) in a Claude Project:

1. **Role:** a documentation editor who reviews and suggests, never rewrites.
2. **Rules:** in house-style.md. There are 23 rules grouped by topic, each with
   a bad and a good example, because examples change model behavior far more
   reliably than abstract rules.
3. **Output format:** a summary, an issues table, an image list, and questions.
4. **Constraints:** quote exactly, never change meaning, don't verify facts,
   don't touch product names or UI text, and trace every change to a rule.

### Test material

- **A planted-error sample:** a short SSO article with 14 known issues.
- **A real legacy help page:** the Installation page of a PowerPoint charting
  add-in I documented years ago, reviewed as HTML so images and links could be
  checked. (The product name is replaced with the placeholder "Contoso Charts.")

### Results across versions

| | v1 | v2 | v3 |
|---|---|---|---|
| Rules | 15 | 22 | 22 (refined) |
| Table rows for the same page | 23 | 44 | **27** + separate image list |
| Images checked for alt text | 0 of 14 | 14 of 14 | 14 of 14, in their own section |
| "Click" issues | 5 rows + a catch-all | 11 rows | **1 pattern row** (11 places) |
| Severity spread (High/Med/Low) | Mostly Medium | 15 / 28 / 1 | **21 / 15 / 5**, matching my editorial scale |
| Fixes applied before open questions were answered | Yes | No ("Pending Q#") | No |

### What each round fixed

| Round | Problem found | Fix |
|---|---|---|
| v1 → v2 | One sentence split into several rows with conflicting fixes | One row per sentence, one combined fix |
| v1 → v2 | A fix applied that its own open question could invalidate | "Pending Q#" instead of a fix |
| v1 → v2 | No rules for alt text, "click here," "we," "as shown below," and more | 7 new rules with real examples |
| v2 → v3 | Grouping needed identical wording, so 11 "Click" rows | Group by pattern |
| v2 → v3 | "Trace every change to a rule" made fixes too literal | If a fix leaves a sentence with no purpose, rewrite it |
| v2 → v3 | Almost everything rated Medium | Severity examples set by my editorial judgment |
| v3 → v4 | Didn't recognize the drafter's markers; misquoted a version number | Marker rules; a self-check on every quote |
| v3 → v4 | Split "choose a location and enter a file name" into two steps | Standard dialog tasks count as one action |
| v4 → v5 | Rules duplicated in two agents could drift apart | All rules moved to house-style.md |

**Severity scale (my call as the editor):** High: passive voice, "click" instead
of "select," missing alt text (a WCAG Level A failure), and anything that could
mislead the reader. Medium: word-list terms such as "e-mail." Low: polish.

### What the reviewer found that I didn't

- The screenshots appear to be out of order (`2.jpg` before `1.jpg`).
- "30Mib" technically means mebibits, a tiny amount of disk space.
- The uninstall procedure never says how to start the uninstaller.

## Part 2: Doc drafter

### The risk it's designed around

A drafter writes new content, so its biggest risk is **inventing facts**: a UI
label, a limit, or a step that sounds right but isn't in any source. Its
instructions are built around traceable accuracy:

| Instruction | Why |
|---|---|
| Use only facts from the sources | Stops guessing |
| Tag every fact with its source (`[S1]`) | Any sentence can be checked in seconds |
| `[GAP: …]` inline where information is missing | It asks instead of inventing |
| `[CONFLICT: …]` when sources disagree | It never quietly picks one |
| Leave out internal information, and list what was left out | No code names, ticket numbers, or internal debates |
| SME checklist: platforms, versions, permissions, errors, limits, result | Catches gaps an experienced writer would ask about |

### Test: a source pack with planted problems

A fictional "Export to PDF" feature with a spec excerpt, a Jira ticket, and SME
call notes. It contains a conflict (50 vs. 20 charts), three gaps, and five
internal items. An answer key was written before the first run.

### Results across versions

| Check | v1 | v2 / v3 |
|---|---|---|
| Conflict flagged, not resolved | ✅ | ✅ |
| Gaps marked or asked about | 2 of 3 (missed platform) | ✅ 3 of 3, via the SME checklist |
| GAP markers placed inline | ❌ separate bullet | ✅ at the affected step |
| Invented facts | None | None |
| Internal items left out and listed | 5 of 5 | 5 of 5 |
| Product named with each version | ❌ | ✅ |
| Save As kept as one step | — | ❌ in v2, ✅ in v3 (after the shared house style) |
| Reviewer issues on the draft | 2 | 2 (v2 draft; one was the Save As split that v3 fixed) |

Its best behavior: the template asks the intro to say *why* the reader would
export to PDF. No source said, so it left the purpose out and told me why,
instead of inventing one.

## Part 3: Doc intake

### The risk it's designed around

The drafter's risk is inventing facts. Intake's risk is **passing along the
wrong facts**: a decision that was later reversed, a feature closed as Won't
Fix, a plan presented as fact, or a customer's name.

| Rule | Why |
|---|---|
| Latest decision wins, and earlier ones go in a Decision log | Reversed decisions don't leak into docs |
| Only what ships | Won't Fix and backlog items stay out |
| Facts, not speculation ("maybe," "next year") | Roadmap hints stay out |
| Remove confidential details completely | No customer names, people, performance numbers, or code names |
| Every fact keeps its evidence, for example (R5, Oct 13) | A writer can trace any fact |
| The reason for a doc goes in a "Why" column, never in a source pack | Internal context doesn't reach customers |
| A [S0] Version block in every pack | The version reaches the doc as a reader-facing fact |
| Questions numbered I-Q#; downstream agents add only new ones (D-Q#) | One question list for the SME, no duplicates |
| End with a scope check | A human approves the doc list before drafting |

### Test: raw inputs with six planted traps

A fictional "Refresh from Excel" feature: a Slack thread where the plan changes
from auto-refresh to manual, meeting notes, a Done ticket and a Won't Fix
ticket, a pull request, and a support email revealing that an existing article
is wrong. An answer key was written before the first run.

### Results across versions

| Check | v1 | v2 | v3 |
|---|---|---|---|
| Final decision used; change logged | ✅ | ✅ | ✅ |
| Won't Fix and speculation excluded | ✅ | ✅ | ✅ |
| No confidential details in source packs | ✅ | ✅ | ✅ |
| Noticed a later source answered an earlier open question | ✅ | ✅ | ✅ |
| Wrong existing article flagged, High priority | ✅ | ✅ | ✅ |
| Reason for a doc kept out of source packs | ❌ | ✅ | ✅ |
| Superseded messages never cited | ❌ | ✅ | ✅ |
| A source pack for every doc, including release notes | ❌ | ✅ | ✅ |
| Drafter repeated intake's questions | Yes | No | No |
| Product version reached the draft | ✅ | ❌ (side effect of a v2 rule) | ✅ via [S0] |
| Unique question numbers across the pipeline | ❌ | ❌ | ✅ I-Q# / D-Q# |

### What intake found beyond the answer key

- A third doc to update: the keyboard shortcuts reference.
- A question a senior writer would ask: what does Refresh All Charts do if one
  linked workbook is missing?

## Part 4: Doc planner

### The risk it's designed around

Intake sees only the new feature. The planner's job is to see the **whole doc
set**, so the team doesn't publish a duplicate article, leave a contradicting
page live, or put a topic in the wrong place.

| Rule | Why |
|---|---|
| Check existing docs before planning anything new | No duplicate articles |
| One action per doc: New, Update, Rewrite, Merge, Retire, or No change | Clear scope for each piece of work |
| Override intake when the inventory shows a better choice, with a reason | The plan reflects the real doc set |
| Read every inventory summary for content that contradicts the new facts | Stale articles get fixed too |
| Link to existing articles that answer open questions | Fewer GAPs and SME questions |
| Keep a rewritten article's title when it still fits | Existing links don't break |
| Drafting briefs with outlines mapped to [S#] facts | The drafter gets structure, not just facts |
| Questions numbered P-Q# | One combined list with I-Q# and D-Q# |
| End with plan approval | The docs lead signs off before drafting |

### Test: intake's output plus an inventory of 14 existing articles

The inventory had eight planted traps, including an existing 2021 article that
already covers refreshing, a troubleshooting page claiming charts update "every
5 minutes," existing articles that answer two intake questions, and two
articles that overlap.

### Results (v1)

| Check | Result |
|---|---|
| Only one refresh article planned (rewrote the 2021 article, kept its title) | ✅ |
| Found the stale troubleshooting article | ✅ |
| Linked to existing articles for an intake question (I-Q2) | ✅ |
| Answered I-Q7 from the inventory | ✅ |
| Added an "Error messages" update intake missed | ✅ |
| Flagged the overlap between two relinking articles | ✅ |
| Placed the topic in the right TOC section | ✅ |
| Release notes in the existing "What's new" page | ✅ |
| Every change to intake's plan has a reason | ✅ |
| Drafting briefs with outlines mapped to [S#] | ✅ |
| Plan summary counts match the table | ❌ (fixed in v2) |

**Planner v2 rerun (same inputs):**

| Check | v1 | v2 |
|---|---|---|
| Summary counts match the table | ❌ | ✅ "two rewrites, five updates, one no change," with a totals line |
| Every brief lists its I-Q# and P-Q# questions | Partly | ✅ all 7 briefs |
| Briefs list the result source for each step | ❌ | ✅ for example "uses [S3], [S1]" |
| All eight planted traps | ✅ | ✅ |

v2 also made a different but defensible structural call: instead of
suggesting a later merge of the two relinking articles, it keeps the relinking
steps in one article and has the other link to it. It dropped v1's optional
note in "Enter data in the data grid." Runs vary, so a plan still needs the
docs lead's review.

**Beyond the answer key (v1):** it planned a note in "Enter data in the data grid,"
asked whether linked charts *ever* updated automatically (which decides how to
word the release note), and noticed the drafter had no Troubleshooting template.

**My decisions as docs lead:** approved the plan, and kept the title "Update
linked chart data" to protect existing links.

### Full pipeline results with the approved plan

| Article | Type | Reviewer issues |
|---|---|---|
| Update linked chart data | Task (Rewrite) | **0** |
| Charts don't update after editing Excel | Troubleshooting (Rewrite) | **3** (passive voice in 5 places, one heading restating the symptom, "typed into") |

### What the planning stage changed elsewhere

| Change | Why |
|---|---|
| Drafter v6: follows a brief's title, outline, and links; drafts only changed passages for an Update; new Troubleshooting template | The planner's briefs need a drafter that can use them |
| Drafter v7: a brief's [S#] list is the main source, not the only one | v6 left out a step's result because the result fact was in a different block |
| house-style v1.1: Troubleshooting titles describe the symptom | Rule 7 required verb-first headings, which doesn't fit troubleshooting |
| Planner v2: summary counts must match the table; each brief lists its questions | v1's summary miscounted, and the drafter repeated questions the brief didn't list. Confirmed in a rerun. |

## Part 5: Doc QA

### The risk it's designed around

Every agent so far checks one document. A release fails in the gaps
**between** documents: a link that uses an old title, a button named two ways,
a release note that contradicts the task article, or a planned article nobody
wrote. The QA agent reads the whole release together, like a release editor
the day before launch.

| Check | Example it guards against |
|---|---|
| Completeness | A planned Update with no draft |
| Brief compliance | A heading order or doc type that doesn't match the plan |
| Links | A link missing from the link map, or a link to a title that doesn't exist |
| Terminology across articles | "Refresh All" in one article, "Refresh All Charts" in another |
| Facts across articles | A release note that contradicts the task article |
| Unsourced facts | A fix that no source supports |
| Message text | An error message quoted with a word missing |
| Open markers | GAPs still waiting on SME questions |
| Release verdict per draft | Ready, Ready after fixes, Blocked, or Missing |

It doesn't repeat the reviewer's sentence-level style checks.

### Test: a release with ten planted defects

The approved plan, link map, source pack, and five drafts: the two real drafts
from the pipeline plus three smaller updates (Error messages, Keyboard
shortcuts, What's new) with planted defects. The answer key also listed things
that are correct, to catch false alarms.

### Results (v1)

| Planted defect | Found |
|---|---|
| Planned article with no draft | ✅ |
| Two links to intake's old title instead of the final title | ✅ both |
| "Refresh All" instead of "Refresh All Charts" | ✅ |
| Release note says refresh works with CSV files (source says .xlsx only) | ✅ |
| Invented fix with no source | ✅ |
| Error message missing "the" | ✅ |
| "Version 4.3" without the product name | ✅ |
| "Ctrl + Alt + R" spacing | ✅ |
| Open GAPs counted, with their question numbers | ✅ |
| False alarms (re-flagging the reviewer's style checks) | ✅ none |

**Verdicts:** Ready 0 · Ready after fixes 2 · Blocked 3 · Missing 1.

**Beyond the answer key:**

- It found a real defect I hadn't planted: the link map requires Error
  messages to link to "Update linked chart data," and neither new entry does.
- It noticed two articles disagree: one gives a fix for "chart is full," the
  other has a GAP in the same place. It recommended a GAP in both until the
  SME answers.
- For the shortcut spacing, it said to check the article's existing rows
  first, the way a senior editor would.
- It said it couldn't check heading order for the two rewrites because their
  briefs weren't in the input, instead of guessing.

## Part 6: Doc maintenance

### The risk it's designed around

Docs go wrong after they're published, as the product keeps changing. A
renamed button breaks every article that mentions it, not just the main one.
SME answers arrive weeks later and could fill open GAPs. Support tickets show
confusion the docs never caused on paper. The maintenance agent watches all
of that and turns it into routed work.

| Rule | Why |
|---|---|
| Sweep for every occurrence of a changed label, message, shortcut, or limit | A rename is wrong in every article that mentions it |
| Answers close gaps | An SME answer fills every GAP waiting on that question |
| Reader signals count | Repeated support tickets point to a clarity problem |
| History stays history | Earlier release notes aren't edited; the new version gets its own entry |
| Versions matter | Add "In Contoso Charts 4.4 and later…" instead of deleting what 4.3 users need |
| Not every change affects the docs | Refactors, speculation, and Won't Fix tickets are listed as no impact |
| Group fixes by cause into change sets with one shared wording (v2) | The same change reads the same in every article |
| Route the change set: Planner, Intake, or Drafter (v2) | Consistent routing for related fixes |
| Hold until release, or Blocked on a question (v2) | Nothing goes live before its version ships |

### Test: seven changes after the 4.3 release

Nine published articles, the open SME questions, and seven changes: approved
4.4 release notes (new shortcut, new Refresh All behavior, a higher export
limit), a pull request renaming Change Source, SME answers to three open
questions, 14 support tickets, an internal refactor, a Slack "maybe," and a
Won't Fix ticket.

### Results

| Check | v1 | v2 |
|---|---|---|
| Shortcut change in both articles, Critical, with a version note | ✅ | ✅ |
| 4.3 release notes left unchanged; new 4.4 entry | ✅ | ✅ |
| Rename sweep: all five articles, including a 2023 article | ✅ | ✅ |
| Export limit change in an article not about refresh | ✅ | ✅ |
| SME answers matched to their GAPs (I-Q4 only partly answered) | ✅ | ✅ |
| Support tickets turned into a clarity fix | ✅ | ✅ |
| Refactor, speculation, and Won't Fix marked no impact | ✅ | ✅ |
| Structure | 16 separate tickets | **7 change sets**, 21 tickets |
| Shared wording for related fixes | ❌ each ticket worded separately | ✅ one wording per change set |
| Consistent routing | ❌ a 2-article fix went to Intake, a 5-article rename to the Drafter | ✅ one route per change set |
| Release timing | One general question | ✅ 4 change sets on Hold until release, 3 Ready now |

**Beyond the answer key:** it noticed the approved 4.4 release notes don't
mention the rename, and that the release notes were still an approved draft,
so changes should wait for the release.

**Run variation:** v1 also asked whether the old shortcut still works as an
alias, and flagged the two overlapping relinking articles for the planner; v2
didn't. Approval is where a human catches that.

## Part 7: Doc publisher

### The risk it's designed around

The publisher creates no content. Its risks are **letting something through
that isn't ready**, and **quietly changing what a writer wrote**. So it acts as
a strict gate with only mechanical permissions.

| Rule | Why |
|---|---|
| Publish only Ready items; Blocked, Missing, and Hold stay out | Nothing unfinished reaches readers |
| Verify every claimed fix against the final text | "Ready after fixes" is checked, not trusted |
| Block any file with [GAP], [CONFLICT], internal question numbers, TBD, or TODO | Internal notes never go live |
| The only allowed removals: [S#] source tags and evidence notes | The writer's words stay exactly as approved |
| Updates become patches with exact placement | It never invents the rest of an article |
| Links come from the site's slug map, never guessed | No broken URLs |
| Redirects only when the plan retires or renames | No invented redirects |
| Flag release risks, and let the docs lead decide | Contradicting old and new pages aren't left live by accident |
| A publication record goes to maintenance | Maintenance knows exactly what's live |

### Test: the final 4.3 release

The release info, front matter schema, slug map, approved plan, final QA
report, two maintenance change sets, and four final drafts, with nine traps:
a fix claimed but not applied, an internal "TBD (I-Q6)" note, evidence notes
to strip, a "Ready" change set with no draft, links to articles outside the
release, no renames (so no redirects), two Updates that must be patches, and
two release risks.

### Results (v1)

| Check | Result |
|---|---|
| Main article published, 14 source tags and 1 evidence note removed, no other wording changed | ✅ |
| Claimed fix not applied ("Refresh All") caught and sent back | ✅ |
| "TBD (I-Q6)" caught; the file held, not edited | ✅ |
| What's new published as a patch | ✅ |
| Blocked and Missing articles held | ✅ |
| Hold change set held; Ready change set with no draft sent to the Drafter | ✅ |
| Links built from the slug map, including articles outside the release | ✅ |
| No redirects invented | ✅ |
| Release risks flagged with recommendations | ✅ 5 risks |
| Front matter matches the schema | ✅ |
| PR description and publication record | ✅ |

**Result:** Publishing 2 (1 full file, 1 patch) · Held back 6 · Redirects 0.

**Beyond the answer key:** it noticed the held "Mac shortcut TBD" note
contradicts the published "Refresh isn't available on Mac," and its
publication record flagged both published texts for the upcoming shortcut
change in 4.4, handing the next job to maintenance.

**Limit:** it could only say the old troubleshooting page *might* contradict
the new article, because the live text of held articles wasn't in its inputs.
That's an input fix, not an instruction fix.

## Part 8: Full-guide run (Installation and Getting started)

The first user guide had two chapters with no source behind them: Installation
and Getting started. Instead of patching the text by hand, I gave the pipeline
the missing inputs and ran it again.

### What changed in the agents

| Agent | Change | Why |
|---|---|---|
| Doc intake **v4** | Handles a **doc request** as well as a product change. Specs and passed test scripts count as sources. Adds **"Needs source"** for any requested topic with no source, and exact UI labels from the latest spec. | v3 only knew how to process changes. A guide also needs existing features. |
| Doc planner **v3** | Adds a **FULL GUIDE** scope with a guide outline. It maps existing articles into chapters, places finished chapters without re-planning them, and follows "no pack, no brief." | v2 planned only the docs that one change affected. |
| house-style.md **v1.2** | Rule 7: titles and headings are short labels (1–4 words). Rule 22: numbered figure captions. | Feedback that the guide's headings read like sentences |

### Test: a doc request with ten planted traps

The test material had:

- the installer and requirement specs, with an earlier version that's superseded
- a passed QA test script and a UI spec
- a label rename (Insert Chart → New Chart)
- a code name, a performance number, and a customer name
- a Won't Fix ticket and an In Progress ticket
- a "might" from Slack

### Results

| Stage | Result |
|---|---|
| Intake v4 | All superseded facts are logged, all confidential items are removed, and the speculation and unshipped tickets are excluded. **It applied "Needs source"** to the first refresh and export, which no raw input covered. One gap was missed: nothing asks what Chart Styles and Color Palette do. |
| Planner v3 | **7/7.** It reused 4 existing articles instead of creating new ones. It found 4 stale articles, one that intake missed. It placed 5 finished chapters, and it sent the sourceless "Choose a chart type" back to intake. |
| Drafter v7 | 5 drafts and **0 invented facts.** Every missing fact is a GAP pointing to an existing question. |
| Reviewer v5 | 8 Medium issues and no High ones. It applied the new rule 7 to **link text** and found two live titles that now break it. |
| QA v1, round 1 | All 5 drafts were blocked by open SME questions. It caught a **disagreement between the reviewer and the brief** about wizard steps, and it caught my own link edit. |
| QA v1, round 2 | After the SME answers and the writer's fixes: **Ready 4 · Ready after fixes 2 · Blocked 0.** It found that What's new never announced Link to Excel or the Welcome pane. |
| Publisher v1 | **Publishing 6 (2 full files + 4 patches) · Held 1 · Redirects 0.** It verified every claimed fix and removed only source tags. It caught a **patch-order bug** that would have left a deleted sentence live. Miss: it didn't flag a bullet added after QA. |
| Maintenance v2 | 3 change sets with 9 tickets. The 4.4.1 rename sweep reached the printed guide's figure, the Windows 10 drop keeps a 4.4 note, and the support signal is Blocked as a question, not stated as fact. All 4 no-impact traps are excluded. |

The full run, with real outputs at every stage, is in
[examples/install-getting-started/](examples/install-getting-started/).
The customer guide ([`outputs/contoso-charts-user-guide.pdf`](outputs/contoso-charts-user-guide.pdf)) now builds its
Installation and Getting started chapters from these traced drafts.

## Lessons learned

1. **The writer's expertise is the product.** The model's style knowledge was
   good from the start. What it needed was an editor's judgment: one comment per
   sentence, don't fix what you've queried, prioritize, and know what to ask an SME.
2. **Every instruction has side effects.** Test each change, then look for what
   it broke.
3. **Input format decides what an agent can see.** Plain text hides images and
   links; HTML exposes them.
4. **Output varies between runs.** Reliable evaluation needs 2–3 runs per test.
5. **Agents need a shared contract.** When one agent's output is another's input,
   they must agree on markers and rules. That's an interface.
6. **Single-source the rules.** Two copies of a style guide drift apart, in agents
   as with writers. One house-style.md file fixed that, the same idea as content
   reuse in DITA.
7. **Fixes cause side effects downstream, too.** An intake rule meant to remove
   roadmap hints also removed the version number from the draft. Test the whole
   pipeline, not just the agent you changed.
8. **Pass questions down the pipeline.** Without a shared list, each agent asks
   the SME the same thing again.
9. **An agent needs to see the existing docs.** Without the inventory, intake
   planned a new article that would have duplicated one from 2021, and missed a
   wrong troubleshooting page entirely.
10. **Strict rules can remove good content.** "Use only the listed sources" made
    the drafter leave out a step's result. Clear rules need room for judgment.
11. **Check the release, not just the article.** The worst defects (wrong link
    titles, contradicting facts, a missing article) only show up when you read
    all the drafts together.
12. **Agents can catch what the answer key missed.** The QA agent found a defect
    I didn't plant, so an answer key is a starting point, not the ceiling.
13. **Docs drift after publishing.** One product rename broke five articles.
    Maintenance needs a sweep, not a single fix.
14. **Group related fixes.** Five separate tickets for one rename risk five
    different wordings. One change set with shared wording keeps them identical.
15. **The last gate should have the fewest permissions.** The publisher may
    only remove tags and build links. Everything else goes back to a human.
16. **Verify, don't trust.** A fix marked as applied wasn't. One check against
    the text caught it.
17. **Know when to stop.** "Good enough to use" beats endless tuning.
18. **Missing content is an input problem, not an agent problem.** The guide's
    unsourced chapters didn't need a smarter drafter. They needed the specs, and
    an intake rule that refuses to fill a pack from general knowledge.
19. **One shared rule changes every agent.** Rewriting house-style rule 7 made the
    reviewer flag link text to two live articles. Version the rules file, and
    retest after every change.
20. **Agents can disagree.** The reviewer and the brief read "one action per step"
    differently. QA caught it, and a human ruled. The fix belongs in the rule,
    not in either agent.

## Files

The latest version of each agent is in `agents/`. Every earlier version is kept
in `agents/history/`, so you can see how each one changed between rounds.

| Path | What it is |
|---|---|
| `house-style.md` | Shared style rules and markers, v1.2 (single source of truth) |
| `agents/intake-agent-v4.md` | Doc intake instructions |
| `agents/planning-agent-v3.md` | Doc planner instructions |
| `agents/doc-drafter-v7.md` | Doc drafter instructions |
| `agents/style-reviewer-v5.md` | Style guide reviewer instructions |
| `agents/qa-agent-v1.md` | Doc QA instructions |
| `agents/publishing-agent-v1.md` | Doc publisher instructions |
| `agents/maintenance-agent-v2.md` | Doc maintenance instructions |
| `agents/history/` | Every earlier version of each agent, plus `house-style-v1.0.md` and `v1.1.md` |
| `examples/refresh-from-excel/` | One full run with real outputs at each stage (see its README) |
| `examples/install-getting-started/` | The full-guide run: all seven stages, including two QA rounds, the publisher, and maintenance |
| `outputs/contoso-charts-user-guide.pdf` | The customer-facing user guide the pipeline produced |
| `outputs/contoso-charts-guide-handover-notes.md` | Internal notes: sources per chapter, and what's still open |
| `case-study/case-study-ai-docs-pipeline.pdf` | One-page case study |
| `case-study/ai-docs-pipeline-report.pdf` | Full report on the design, tests, and results |
| `tests/sample-draft-sso.md` | Reviewer test draft with planted errors |
| `tests/source-pack-export-pdf.md`, `tests/drafter-answer-key.md` | Drafter test inputs (planted conflict, gaps, internal items) and answer key |
| `tests/raw-inputs-data-refresh.md`, `tests/intake-answer-key.md` | Intake test inputs with six planted traps, and answer key |
| `tests/planning-inputs-data-refresh.md`, `tests/planning-answer-key.md` | Planner test inputs (intake output and a docs inventory) and answer key |
| `tests/qa-inputs-data-refresh.md`, `tests/qa-answer-key.md` | QA test inputs (plan, link map, source pack, five drafts) and answer key |
| `tests/publishing-inputs.md`, `tests/publishing-answer-key.md` | Publisher test inputs (release info, slug map, plan, QA report, drafts) and answer key |
| `tests/maintenance-inputs.md`, `tests/maintenance-answer-key.md` | Maintenance test inputs (published docs, open questions, seven changes) and answer key |
| `tests/*-install*.md` | Inputs and answer keys for the full-guide run (intake v4, planner v3, drafter, publisher, maintenance) |

All products, customers, and people in the test material are fictional. Answer
keys were written before each agent was run.

## Roadmap

| Stage | Agent | Status |
|---|---|---|
| 1. Intake | Doc intake v4 | ✅ Built and tested |
| 2. Planning | Doc planner v3 | ✅ Built and tested |
| 3. Drafting | Doc drafter v7 | ✅ Built and tested |
| 4. Review | Style guide reviewer v5 | ✅ Built and tested |
| 5. QA | Doc QA v1 | ✅ Built and tested |
| 6. Publishing | Doc publisher v1 | ✅ Built and tested |
| 7. Maintenance | Doc maintenance v2 | ✅ Built and tested |

All seven stages are built (Phase A of my learning plan: agents without code).

### Small improvements to make

- Give the publisher the live text of related articles, so it can confirm
  release risks instead of saying "might."
- Give QA the complete plan, including every brief.
- Publisher v2: content added after the QA report needs its own QA verdict.
- Decide a patch-release policy (M-Q1) before 4.4.1 ships.
- house-style v1.3: add "A wizard page counts as one step" to rule 9.
- Replace house-style.md v1.1 in the QA, publisher, and maintenance projects.
- Ask what Chart Styles and Color Palette do. Intake and the drafter both missed it.
- Run each test 2–3 times and record the variation.

### Next phases

- **Phase B:** connect the stages with a visual workflow tool (n8n or Make), so
  each agent's output moves to the next automatically.
- **Phase C:** rebuild the pipeline in Python with AI-assisted coding, run it
  from GitHub pull requests, and measure it across a larger test set with
  several runs per test.
