# AI documentation pipeline: user documentation

This is the user documentation for the [AI documentation pipeline](README.md). It's organized with the [Diátaxis framework](https://diataxis.fr/), so each section serves one need:

| Section | Use it when you want to… |
|---|---|
| [Tutorial](#tutorial) | learn the pipeline by running it once, start to finish |
| [How-to guides](#how-to-guides) | get a specific job done |
| [Reference](#reference) | look up what an agent takes, produces, or marks |
| [Explanation](#explanation) | understand why the pipeline works the way it does |

The main [README](README.md) is the case study: what I built, how I tested it, and the results.

---

## Tutorial

### Run your first pipeline

In this tutorial, you run the first four stages of the pipeline on a small, made-up product change: a "Refresh from Excel" feature in Contoso Charts. You'll go from raw notes to a reviewed draft and compare your results with the outputs in [`examples/refresh-from-excel/`](examples/refresh-from-excel/).

It takes about an hour. You need a Claude account with access to Projects. Nothing else is required: the agents are instructions, not code.

#### 1. Set up the Doc intake agent

1. In Claude, create a project named **Doc intake**.
2. Open [`agents/intake-agent-v4.md`](agents/intake-agent-v4.md), copy everything, and paste it into the project's instructions.

#### 2. Run intake on the raw material

1. Open [`tests/raw-inputs-data-refresh.md`](tests/raw-inputs-data-refresh.md) and copy everything below the line.
2. Start a chat in the **Doc intake** project and paste it.

Intake returns a doc impact table, a source pack for each doc, a decision log, a list of excluded items, and questions numbered I-Q1, I-Q2, and so on.

3. Check one thing before you go on: the raw material changes its mind about auto-refresh partway through the Slack thread. The source packs should use the final decision (manual refresh), and the earlier one should appear only in the decision log.

This is the first human checkpoint: as the writer, you confirm the scope before anything is planned.

#### 3. Plan the docs

1. Create a project named **Doc planner** and paste [`agents/planning-agent-v3.md`](agents/planning-agent-v3.md) into its instructions.
2. Start a chat and paste two things: intake's full output from step 2, and the existing docs inventory from [`tests/planning-inputs-data-refresh.md`](tests/planning-inputs-data-refresh.md).

The planner returns a doc plan, one drafting brief per doc, and a link map. Notice that it rewrites an existing 2021 article instead of planning a new one. That's the duplicate it was designed to catch.

This is the second checkpoint: you approve the plan.

#### 4. Draft one article

1. Create a project named **Doc drafter**. Paste [`agents/doc-drafter-v7.md`](agents/doc-drafter-v7.md) into its instructions, and add [`house-style.md`](house-style.md) as a project file.
2. Start a chat and paste the drafting brief for **Update linked chart data**, the source pack it names, and intake's question list under the heading "Already asked (don't repeat)."

The draft tags every sentence with its source, such as `[S1]`, and marks missing information as `[GAP: … — see I-Q#]` instead of guessing.

#### 5. Review the draft

1. Create a project named **Style guide reviewer**. Paste [`agents/style-reviewer-v5.md`](agents/style-reviewer-v5.md) into its instructions, and add the same `house-style.md` as a project file.
2. Paste the draft from step 4.

The reviewer returns a summary, an issues table that cites house-style rules by number, and the list of open GAPs. It doesn't rewrite the draft.

#### 6. Compare your results

Open [`examples/refresh-from-excel/`](examples/refresh-from-excel/) and compare your outputs with files 02 to 05. Wording will differ from run to run. What should match:

- the final decision was used, and Won't Fix items were excluded
- no fact in the draft lacks a source tag
- every GAP points to a question number

You've now run intake, planning, drafting, and review. To run QA, publishing, and maintenance, see the [how-to guides](#how-to-guides).

---

## How-to guides

### Run the later stages

1. Create a project for each agent in [`agents/`](agents/): `qa-agent-v1.md`, `publishing-agent-v1.md`, and `maintenance-agent-v2.md`. Add `house-style.md` as a project file for QA.
2. Give each agent the inputs listed for it in the [agent reference](#agents).
3. Use the matching files in [`tests/`](tests/) as inputs, and compare your results with the answer keys there.

### Change a style rule

1. Edit the rule in [`house-style.md`](house-style.md). Never put a style rule in an agent's instructions.
2. Increase the version number at the top of the file.
3. Upload the new file to every project that uses it: planner, drafter, reviewer, and QA.
4. Rerun at least one test, and check what the change broke as well as what it fixed.

### Add a test case

1. Write the raw input as a short scenario, and plant the problems you want the agent to catch, for example a reversed decision or a missing fact.
2. Write the answer key **before** you run the agent: what it must find, and what it must not flag.
3. Run the agent two or three times. Output varies between runs, so one good run isn't proof.
4. Save the input and the answer key in [`tests/`](tests/).

### Resolve a gap or conflict

1. Find the question the marker points to, for example `[GAP: … — see I-Q4]`.
2. Get the answer from the SME.
3. Replace the marker with the answered fact, and add a source tag for the answer.
4. For a `[CONFLICT: …]`, confirm which source is right with the SME. Never pick one yourself.

The publisher blocks any file that still contains a GAP or CONFLICT, so nothing unresolved reaches readers.

### Route a change after publishing

1. Give the maintenance agent the change material, labeled [C1], [C2], and so on, and the published docs.
2. Review its change sets. Each one groups related fixes with one shared wording and a route: Intake, Planner, or Drafter.
3. Approve the ones marked **Ready**. Leave **Hold until release** sets until the version ships.

---

## Reference

### Agents

| Stage | Agent | Receives | Produces |
|---|---|---|---|
| 1 | [Doc intake](agents/intake-agent-v4.md) | Raw material labeled [R1], [R2]… (chat, notes, tickets, pull requests, specs, test scripts) | Doc impact, source packs with evidence, decision log, excluded items, I-Q# questions |
| 2 | [Doc planner](agents/planning-agent-v3.md) | Intake output, existing docs inventory, scope (CHANGE or FULL GUIDE) | Doc plan, drafting briefs, link map, P-Q# questions |
| 3 | [Doc drafter](agents/doc-drafter-v7.md) | Source material [S1], [S2]…, doc type, drafting brief, already-asked questions | Draft with source tags and markers, D-Q# questions |
| 4 | [Style guide reviewer](agents/style-reviewer-v5.md) | A draft, `house-style.md` | Summary, issues table, image check, questions |
| 5 | [Doc QA](agents/qa-agent-v1.md) | Approved plan, all drafts for the release, source packs, `house-style.md` | A release verdict per draft, link and terminology checks, blocking questions |
| 6 | [Doc publisher](agents/publishing-agent-v1.md) | QA report, final drafts, plan, slug map, change sets, front matter schema | Publish-ready Markdown files, patches, pull request description, publication record |
| 7 | [Doc maintenance](agents/maintenance-agent-v2.md) | Change material [C1], [C2]…, published docs, open questions | Change sets with shared wording, routes, and status |

### Markers

| Marker | Added by | Meaning |
|---|---|---|
| `[S#]` | Drafter | The source of the fact in this sentence |
| `[GAP: …]` | Drafter | Information is missing. Points to a question. |
| `[CONFLICT: …]` | Intake, drafter | Sources disagree, and the agent didn't choose |
| `Pending Q#` | Reviewer | A fix waits for a question to be answered |

The publisher removes `[S#]` tags and evidence notes, and blocks any file that still contains a GAP or CONFLICT.

### Question numbers

| Prefix | Raised by |
|---|---|
| I-Q# | Intake |
| P-Q# | Planner |
| D-Q# | Drafter |

Each agent adds only new questions, so the SME gets one combined list with no duplicates.

### Release verdicts

| Verdict | Meaning |
|---|---|
| Ready | Publish as is |
| Ready after fixes | Publish only after every listed fix is in the text. The publisher checks each one. |
| Blocked | Don't publish. An open question or defect remains. |
| Missing | A planned doc has no draft |

### Change set status

| Status | Meaning |
|---|---|
| Ready | Can go live now |
| Hold until release | Waits until its product version ships |
| Blocked | Waits on an open question |

### Human checkpoints

1. Confirm the scope after intake.
2. Approve the plan.
3. Edit each draft.
4. Sign off the release after QA.
5. Approve the merge after publishing.
6. Approve maintenance tickets.

### Files

See the [Files table in the README](README.md#files).

---

## Explanation

### Why every fact is tagged

A language model's main risk in documentation is a fact that sounds right but isn't in any source: a UI label, a limit, a step. Tagging every sentence with its source makes each claim checkable in seconds, and it changes the drafter's behavior: when no source supports a fact, it writes a GAP instead of inventing one.

### Why the agents share one rules file

When the planner, drafter, reviewer, and QA each carried their own copy of the style rules, the copies drifted apart, the same way two writers' style guides do. Keeping one `house-style.md` means a rule changes once and applies everywhere. It's the same idea as content reuse in DITA, applied to AI instructions.

### Why the agents agree on markers

Each agent's output is the next agent's input. The markers, question numbers, and verdicts work like an interface: if one agent writes `[GAP]` and the next doesn't recognize it, the chain breaks. Several fixes in the version history were about this contract, not about writing quality.

### Why a person approves at six points

The agents check, flag, and route. They don't decide what's true or what ships. Each checkpoint is a decision a docs lead would make anyway: scope, plan, wording, release, merge, and maintenance. The agents prepare the decision so it takes minutes instead of hours.

### Why tests use planted traps and answer keys

A run that looks good proves little. Writing the answer key before the run, with traps the agent must catch and correct content it must leave alone, turns "this looks fine" into a result you can count. Output varies between runs, so each test is worth running two or three times.

### Limits

- The agents run by hand in Claude Projects. They aren't connected to Git, Jira, or a docs site yet; that's the next phase on the [roadmap](README.md#roadmap).
- The test material is constructed. The products, customers, and people are fictional.
- An agent can only check what's in its input. For example, the publisher can't confirm a contradiction in an article it wasn't given.
