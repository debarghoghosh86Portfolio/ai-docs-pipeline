# Stage 6 output: Doc publisher v1

**Input:** [publishing-inputs-install.md](../../publishing-inputs-install.md), which has:

- the release info and slug map, including the new System requirements slug
- the plan excerpt
- the QA round 2 report
- the final drafts

**Agent:** Doc publisher v1 (`publishing-agent-v1.md`)
**Run:** Claude Projects, November 2026. The release summary, manifest, and risks are copied verbatim. The full files and patches are summarized.

---

## Release summary (verbatim)

Six of the seven planned articles pass the gate. That includes two full files (System requirements and Install Contoso Charts) and four patches (Contoso Charts overview, Create a chart, Link a chart to Excel data, and What's new in Contoso Charts). Choose a chart type is held because QA marked it Missing. Holding it leaves one known contradiction live, described in Section 7. Every claimed fix was found in the final text. No draft contains blocking markers. The only text removed is source tags.

**Publishing 6 (2 full files + 4 patches) · Held back 1 · Patches 4 · Redirects 0**

## Release manifest

| Article | Action | QA verdict | Gate result |
|---|---|---|---|
| System requirements | New | Ready | Publish (`/getting-started/system-requirements`) |
| Install Contoso Charts | Rewrite | Ready | Publish (full file) |
| Contoso Charts overview | Update | Ready | Publish (patch). Change 2 must be applied before Change 1. |
| Create a chart | Update | Ready after fixes | Publish (patch). QA-14 was found in the text. |
| Link a chart to Excel data | Update | Ready | Publish (patch) |
| What's new in Contoso Charts | Update | Ready after fixes | Publish (patch). QA-15, QA-16, and the docs lead's bullet were found in the text. |
| Choose a chart type | Update | Missing | Hold |

## Gates

- **Fixes:** every claimed fix (QA-14, QA-15, and QA-16) was checked against the text.
- **Removed text:** 74 source tags in total. Nothing else was removed.
- **Blocking items:** no GAP, CONFLICT, TBD, or internal question number remains.
- **Front matter:** it matches the schema, and `product_version: "4.4+"` is set on the two full files.
- **Links:** every "see [title]" is turned into a link from the slug map.

## Release risks (verbatim, shortened)

1. **Choose a chart type is held, but Create a chart links to it.** The live article probably still says "Insert Chart" and lists four types. The publisher recommends **against** holding Create a chart. Holding it "would point readers to a Create a chart article that still says 'Insert Chart,' while the overview says New Chart. That would be a worse contradiction."
2. **Old UI wording may remain in parts of the site I can't see.** It recommends searching the repository for "Insert Chart" and "Select Data" before merging.
3. **The overview patch depends on the order of changes.** "Change 2 must run before Change 1. Otherwise the sentence Change 2 is meant to delete becomes 'Select New Chart to add a chart.' and survives."

## Publication record (for maintenance)

| Article | Slug | Product version | Published |
|---|---|---|---|
| System requirements | /getting-started/system-requirements | 4.4+ | Yes (new) |
| Install Contoso Charts | /getting-started/install | 4.4+ | Yes (rewrite) |
| Contoso Charts overview | /getting-started/overview | existing value kept | Yes (patch) |
| Create a chart | /create-charts/create-chart | existing value kept | Yes (patch) |
| Link a chart to Excel data | /work-with-data/link-chart-to-excel | existing value kept | Yes (patch) |
| What's new in Contoso Charts | /getting-started/whats-new | 4.4 entry updated | Yes (patch) |
| Choose a chart type | /create-charts/chart-types | unchanged | No (held) |

---

## Scored

| Check | Result |
|---|---|
| Only Ready and Ready-after-fixes items published, with Missing held | ✅ |
| Claimed fixes verified against the text | ✅ All 3 |
| Only source tags removed | ✅ 74 tags removed, and no wording changed |
| New slug used, and no redirects invented | ✅ |
| Release risks flagged, with the decision left to the docs lead | ✅ 3 risks |

**Beyond expectations:** the **patch-order bug** in risk 3. Applied in the order written, the overview patch would have turned the sentence it was meant to delete into "Select New Chart to add a chart." That sentence would then have stayed live. No other agent noticed this.

**A miss:** the docs lead added a What's new bullet *after* QA round 2. The publisher confirmed the bullet was present, but didn't flag that it never went through QA. Unchecked content got through the gate. **Proposed for publisher v2:** any text added after the QA report needs a QA verdict of its own.
