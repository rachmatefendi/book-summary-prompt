# Book Summary Prompt

A reusable prompt for turning books, papers, reports, handbooks, SOPs, and reference documents into **source-faithful, structured, compact, and traceable Markdown summaries**.

**Current release:** `v1.0`

The repository is prompt-first. Its main artifact is [`PROMPT.md`](./PROMPT.md). If you also maintain a long-lived collection of summaries, [`LIBRARY.md`](./LIBRARY.md) adds optional operating rules for IDs, revisions, dependencies, and indexes. Those library rules are intentionally kept out of the runtime summarization prompt.

## Repository contents

- [`PROMPT.md`](./PROMPT.md) — the authoritative runtime prompt to copy into an LLM session, Project Instructions, or system prompt.
- [`LIBRARY.md`](./LIBRARY.md) — optional library-maintenance conventions. Do not include it in every summarization session unless you actually need library lifecycle behavior.
- [`SAMPLE_OUTPUT.md`](./SAMPLE_OUTPUT.md) — a synthetic **T2 Framework / Model / Method** example. It demonstrates one output form, not the universal format for all documents.
- [`LICENSE`](./LICENSE) — MIT License.

## What the prompt is designed to prevent

The prompt is intentionally strict about source fidelity. It is designed to reduce common failure modes such as:

- filling source gaps from model memory;
- turning an author's heuristic into a tested rule;
- inventing formulas, thresholds, KPIs, or process steps to complete a template;
- treating a reported number as independently verified fact;
- claiming full-source coverage when only excerpts were inspected;
- forcing every document into a decision framework or linear workflow;
- collapsing different source types into one generic summary format.

## How to use

1. Copy the full contents of [`PROMPT.md`](./PROMPT.md) into the instruction layer available in your LLM environment.
2. Attach or provide the source document(s).
3. Ask for a summary. A minimal request is enough:

```text
Summarize this document using the Book Summary Prompt.
```

You can also override focus or depth without changing the fidelity rules:

```text
Create a deep summary focused on the main framework, assumptions, and failure conditions.
```

```text
Summarize all documents in this batch, then create a cross-document synthesis only where the relationships are actually supported.
```

## Template routing

The prompt routes by the **dominant form of knowledge**, not by topic alone.

| Template | Primary use |
|---|---|
| T1 | Argument, concept, descriptive, historical, or philosophical sources |
| T2 | Frameworks, models, and analytical methods |
| T3 | Decision principles or pattern / heuristic catalogs |
| T4 | Systems, architecture, engineering, and technical mechanisms |
| T5 | Research and evidence-based documents |
| T6 | Procedures, SOPs, operational manuals, and playbooks |
| T7 | One-page / retrieval briefs |
| T8 | Cross-document synthesis |

A document may use one primary template plus limited conditional modules where materially necessary.

## Core claim labels

The prompt separates four kinds of claims:

- `Source-Reported` — definitions, descriptions, procedures, data, or results reported by the source. This does **not** mean independently verified.
- `Author's Argument` — the author's thesis, interpretation, explanation, or normative position.
- `Author's Heuristic` — a rule or pattern presented from experience or observation; its validation status must follow what the source actually reports.
- `Curator Inference` — a conclusion, application, or derived structure produced from stated source premises.

## Coverage

The prompt distinguishes:

- `full` — all substantive source sections relevant to the summary were actually inspected;
- `partial` — only part of the source was inspected or material parts were unreadable;
- `summary_only` — the work is based on an earlier summary rather than the primary source;
- `unavailable` — the source content could not be inspected.

Having a complete file available is not, by itself, evidence of `full` coverage.

## Output language

The runtime prompt defaults to **English**. Technical terms may remain in their original form when that preserves precision. A user can explicitly request another language.

## Length defaults

- T1–T6: typically 700–900 words of main content.
- T7: typically 300–450 words.
- T8: proportional to the number and relevance of sources.

These are compression targets, not hard limits. Important qualifiers, exceptions, evidence boundaries, and failure conditions take priority over word count.

## Sample

[`SAMPLE_OUTPUT.md`](./SAMPLE_OUTPUT.md) is intentionally synthetic and demonstrates T2 only. It is not a claim that every source should look like that example.

## Optional library mode

If you are building a persistent collection rather than producing one-off summaries, use [`LIBRARY.md`](./LIBRARY.md) for:

- stable record IDs;
- revision numbers;
- dependency tracking;
- relations between summaries;
- derived brief / synthesis lifecycle;
- an optional library index.

Keeping these rules separate makes the runtime prompt easier to copy, inspect, and retain in context.

## License

MIT. See [`LICENSE`](./LICENSE).
