# `plan-brief.md` — human-scannable plan summary

`plan-brief.md` sits beside `plan.md` under `context/changes/<change-id>/`. It is the **human companion** — a glanceable summary a reader can absorb in under a minute without opening the full plan. Written by `dx-plan` at the same time as `plan.md`, derived from its contents, never maintained independently.

## Shape

```markdown
# <change title>

> <one plain-language sentence: what this change does and why>

## What changes

- <concrete thing that will be different — a file, a behavior, an endpoint, a table>
- <another>
- ...

## Phases

<A compact view of the execution path. Use the format that fits the plan's
complexity — a numbered list for 1–3 phases, an ASCII flow for 4+:>

  1 ─── 2 ─── 3 ─── 4
  seed    wire   test   cleanup
  schema  API    e2e    docs

<Below the flow, one line per phase — what it delivers, not how:>

1. **<name>** — <what this phase delivers, one sentence>
2. **<name>** — ...

## Risks & gotchas

- <non-obvious thing drawn from Priors & gotchas or Failure modes>
- <another, if any>

<Omit this section entirely when the plan has no priors, failure modes, or
non-obvious risks. Never write "none.">

## Key decisions

- **<decision>** — <why, in one sentence>
- <another, if any>

<Draw from the Approach section and the interview's resolved questions.
Keep to 1–3 entries — the ones a reader would ask "why not the other way?">
```

## Writing rules

- **Short sentences only.** No prose paragraphs — every line is a scannable bullet or a one-liner.
- **Concrete over abstract.** "Adds `pricing_tier` column to `accounts`" beats "updates the data model."
- **Derived, not maintained.** The brief is regenerated whenever `plan.md` is rewritten (after review-triage edits, for instance) — it has no state of its own.
- **Omit empty sections.** Same rule as `plan.md`: never write a section heading followed by "N/A" or "none."
- **ASCII art is welcome** for phase flows, dependency arrows, before/after diagrams — anything that helps a human see the shape at a glance. Keep it simple; no box-drawing beyond what a monospace font can render clearly.
- **Scale with the plan.** A trivial single-phase plan gets a brief that's 5–8 lines total — just the summary, one phase, and maybe one decision. Don't pad.
