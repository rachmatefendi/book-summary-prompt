# Optional Library Operating Guide

This file is **not part of the runtime summarization prompt**. Use it only when maintaining a persistent collection of summary records over time.

The summarization behavior lives in [`PROMPT.md`](./PROMPT.md). This guide adds lightweight operational conventions for identity, revisions, dependencies, relations, and indexing.

## 1. Library model

Use one summary record per source / edition by default.

Keep derived artifacts separate:

- full summary;
- one-page brief;
- cross-document synthesis;
- optional companion catalog or chapter-level artifact when genuinely needed.

Topic is metadata, not identity. Do not duplicate the same summary into multiple topic folders merely because it has multiple categories.

## 2. Stable record identity

For persistent libraries, add these fields to the YAML header produced by `PROMPT.md`:

```yaml
record_id: "[stable identifier]"
record_type: "summary"
prompt_version: "1.0"
revision: 1
depends_on: []
```

Rules:

- `record_id` remains stable for the same representation and edition even if the filename or category changes.
- A different edition or translation gets a new `record_id`.
- `record_type` may be `summary`, `brief`, or `synthesis`.
- `revision` tracks changes to the record content, not the prompt version.
- `depends_on` is used only for derived artifacts.

Example dependency:

```yaml
depends_on:
  - record_id: "summary-constraint-loop-en-1e"
    revision: 2
    anchor: "Primary Framework"
```

## 3. Filenames

Recommended patterns:

```text
[Category]_[ShortTitle]_Summary_vN.md
[Category]_[ShortTitle]_OnePage_vN.md
CrossDocument_[Topic]_Synthesis_vN.md
```

The filename is for human organization. `record_id` is the stable identity when library mode is used.

A category prefix in a filename is therefore compatible with stable record identity; changing the category may rename the file without changing the record itself.

## 4. Revisions

Increment `revision` when the record changes materially, for example:

- source coverage expands;
- attribution is corrected;
- a material omission is repaired;
- a newer source edition requires a new record rather than overwriting the old one.

Do not increment the summary revision merely because `PROMPT.md` receives a patch release if the summary content itself is unchanged.

## 5. Derived artifacts and dependency review

A brief or synthesis may depend on one or more parent summaries.

When a parent summary changes after a derived artifact was created, mark the derived artifact as `needs_review`. Do not claim that it has automatically incorporated the new parent content.

Suggested catalog statuses:

- `ready`
- `partial`
- `needs_review`
- `superseded`
- `blocked`

`ready` means the record passed internal checks for its stated coverage. It is not independent verification that every source claim is true.

## 6. Relations

Use a small controlled vocabulary:

- `overlaps_with`
- `complements`
- `contradicts`
- `derived_from`
- `revises`
- `same_work_as`

A relationship should name the connected concept and, where available, a supporting source anchor.

Do not infer substantive overlap from title or keyword similarity alone.

Before using `contradicts`, check whether the sources differ in definition, population, setting, period, horizon, or claim type.

## 7. Optional index

A persistent library may maintain a single `Library_Index.md` or equivalent database/table.

Minimum record columns:

| Record ID | Title / edition | Category | Template / mode | Coverage | Revision | Status | Filename |
|---|---|---|---|---|---|---|---|

Optional dependency table:

| Derived record | Parent record | Parent revision used | Current parent revision | Review status |
|---|---|---|---|---|

Optional relation table:

| From | Relation | To | Concept / reason | Source anchor |
|---|---|---|---|---|

The repository does not include an index by default because an empty index adds little value to the reusable prompt package.

## 8. Library boundaries

Do not claim that a file, index, or relation was stored, updated, or synchronized unless that action actually occurred.

Do not assume the entire library is available to the model merely because an index lists its records.

Do not automatically rewrite old summaries when the prompt changes. Apply a new prompt version to new records and to revisions explicitly requested or justified by a material defect.

## 9. When to split the library guide further

Keep this guide as one optional file while one workflow and one maintainer can manage it comfortably.

Only split it into separate operational documents when there is a real maintenance need such as:

- different maintainers;
- different release cycles;
- substantial domain-specific operating requirements;
- file size or review complexity that materially harms usability.

Do not create topic-specific operating manuals merely because the library contains AI, finance, history, or strategy sources.
