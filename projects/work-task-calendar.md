---
layout: default
title: Work Task Calendar
---

## Work Task Calendar

[← Back to portfolio](/)

**Problem.** The maintenance material requisition report is one row per part per
task — roughly 14,000 rows a quarter. Everything needed to answer "which jobs
this week are short of parts?" is in there, but answering it meant pivoting the
export by hand every time, so in practice nobody did.

**Approach.** Collapsed the rows into one card per work order task, dated by
required date, and rolled the part lines up into a single issue status: all
issued, some issued, or nothing issued. A week view shows the whole scheduled
week; a day view expands one date into full part-level rows with on-hand,
required, reserved and issued quantities alongside inventory and issued cost.
Search runs across work order, task, object, part number and description, and
reports matches falling outside the current week so a search never silently
returns nothing.

**Result.** Which tasks can't proceed is visible without touching a
spreadsheet. Planners can see a short part before the shift rather than at it.

**Stack.** Vanilla JavaScript with no dependencies. CSV parser that resolves
columns by header name with alias fallbacks, so an export with renamed or
reordered columns still loads. The page captures its own untouched source on
load, which is what lets the export produce a genuinely self-contained HTML
file — data included, no server, no build step.

**A problem worth describing.** This report has no cost centre column. The code
has to be inferred from the requisitioner signature, and the department from
the code:

```
Signature  →  cost center code  →  department
```

Version 14 made both halves editable in the interface, since a hard-coded
signature table is useless at any terminal but the one it was written for.
Assignments are validated, applied without a reload, and written into the
exported file so an exported copy reopens with them. The port is covered by
three headless browser test suites — 61 assertions across the editor,
filtering, duplicate rejection, export persistence, and a full round trip that
reopens an exported file, edits it again and re-exports.

> **About the data.** This demo runs on generated data. Work order numbers,
> part numbers, descriptions, costs, equipment IDs and people are synthetic —
> only the structure and statistical shape of the original are preserved.

<p><a class="launch" href="/demos/work-task-calendar-anonymized.html" target="_blank" rel="noopener">Launch the demo →</a></p>
<img class="hero" src="/images/work-task.png" alt="Purchase order calendar">
