# AI Documentation Pipeline: Six Agents from Raw Material to Maintained Docs

**Author:** Debargho Ghosh, Technical Writer (16 years, internal and external documentation)
**Status:** Six of seven stages of an end-to-end AI documentation pipeline are
working: Intake (v3), Planning (v2), Drafting (Doc drafter v7), Review (Style
guide reviewer v5), QA (v1), and Maintenance (v2). Publishing is next (see the
Roadmap). Planner, drafter, reviewer, and QA share one house style (v1.1).

## Summary

I designed, tested, and connected six AI agents that support the
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
notes) untouched.

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
                     [Publishing — next on the roadmap]
                                │
                                ▼
New changes + published docs ──► Doc maintenance ──► change sets (Ready / Hold / Blocked)
                                                          │
                     routed back to Intake, Planner, or Drafter ◄──┘   (the loop)

Shared by the planner, drafter, reviewer, and QA: house-style.md (one set of rules)
```

Stages built so far: 1 to 5 and 7 of the full lifecycle.

**Intake** → **Planning** → **Drafting** → **Review** → **QA** → Publishing → **Maintenance**

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
15. **Know when to stop.** "Good enough to use" beats endless tuning.

## Files

The latest version of each agent is in `agents/`. Every earlier version is kept
in `agents/history/`, so you can see how each one changed between rounds.

| Path | What it is |
|---|---|
| `house-style.md` | Shared style rules and markers, v1.1 (single source of truth) |
| `agents/intake-agent-v3.md` | Doc intake instructions |
| `agents/planning-agent-v2.md` | Doc planner instructions |
| `agents/doc-drafter-v7.md` | Doc drafter instructions |
| `agents/style-reviewer-v5.md` | Style guide reviewer instructions |
| `agents/qa-agent-v1.md` | Doc QA instructions |
| `agents/maintenance-agent-v2.md` | Doc maintenance instructions |
| `agents/history/` | Every earlier version of each agent, plus `house-style-v1.0.md` |
| `tests/sample-draft-sso.md` | Reviewer test draft with planted errors |
| `tests/source-pack-export-pdf.md` | Drafter test inputs with a planted conflict, gaps, and internal items |
| `tests/drafter-answer-key.md` | Expected drafter results, written before testing |
| `tests/raw-inputs-data-refresh.md` | Intake test inputs with six planted traps |
| `tests/intake-answer-key.md` | Expected intake results, written before testing |
| `tests/planning-inputs-data-refresh.md` | Planner test inputs: intake output and an existing docs inventory |
| `tests/planning-answer-key.md` | Expected planner results, written before testing |
| `tests/qa-inputs-data-refresh.md` | QA test inputs: plan, link map, source pack, and five drafts |
| `tests/qa-answer-key.md` | Expected QA results, written before testing |
| `tests/maintenance-inputs.md` | Maintenance test inputs: published docs, open questions, and seven changes |
| `tests/maintenance-answer-key.md` | Expected maintenance results, written before testing |

All products, customers, and people in the test material are fictional.

## Roadmap

| Stage | Agent | Status |
|---|---|---|
| 1. Intake | Doc intake v3 | ✅ Built and tested |
| 2. Planning | Doc planner v2 | ✅ Built and tested |
| 3. Drafting | Doc drafter v7 | ✅ Built and tested |
| 4. Review | Style guide reviewer v5 | ✅ Built and tested |
| 5. QA | Doc QA v1 | ✅ Built and tested |
| 6. Publishing | Doc publisher | 🔜 **Next** |
| 7. Maintenance | Doc maintenance v2 | ✅ Built and tested |

### Next: Stage 6, Publishing

The publishing agent will be the gate between QA and the live docs site:

- **Publish only what's ready:** take the drafts QA marks Ready and the
  maintenance change sets marked Ready. Anything Blocked or on Hold stays out.
- **Clean the files:** remove every internal marker (`[S#]` source tags,
  `[GAP]`, `[CONFLICT]`, evidence notes) and refuse to publish if a GAP or
  CONFLICT is still open.
- **Add metadata:** front matter such as title, description, product version,
  TOC location, last-updated date, and keywords.
- **Prepare the change:** publish-ready Markdown files and a pull request
  description for a docs-as-code repo, listing every new, updated, retired,
  and redirected article.
- **Hand off to maintenance:** record what was published, in which version, so
  the maintenance agent knows exactly what's live.

### After that

- **Phase B:** connect the stages with a visual workflow tool (n8n or Make), so
  each agent's output moves to the next automatically.
- **Phase C:** rebuild the pipeline in Python with AI-assisted coding, run it
  from GitHub pull requests, and measure it across a larger test set with
  several runs per test.
