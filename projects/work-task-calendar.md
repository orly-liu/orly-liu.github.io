---
layout: default
title: Work Task Calendar
---

## Work Task Calendar

[← Back to portfolio](/)

**Problem.** The old maintenance material requisition report is one row per part per
task, roughly 14,000 rows a quarter. Everything needed to answer "which jobs
this week are short of parts?" is in there, but it meant pivoting the
entire export by hand every time.

**Approach.** Collapsed the rows into one card per work order task, and rolled 
the part lines up into issue status: all
issued, some issued, or nothing issued. A week view shows the whole scheduled
week with expandable WT cards; a day view expands one date into full part-level rows with on-hand,
required, reserved and issued quantities, inventory and issued cost.
Search runs across work order, task, object, part number, and description, supporting off-week search.

**Result.** Provides visibility on work task status without the need to touch a
spreadsheet. Planners can see a short part before the shift rather than at it.

**Stack.** Vanilla JavaScript with no dependencies. CSV parser that resolves
columns by header name with alias fallbacks. The page captures its own untouched source on
load, which is what lets the export produce a self-contained HTML
file. No server or installation is required.

```

> **About the data.** This demo runs on generated data. Work order numbers,
> part numbers, descriptions, costs, equipment IDs and people are synthetic —
> only the structure and statistical shape of the original are preserved.

<p><a class="launch" href="/demos/work-task-calendar-anonymized.html" target="_blank" rel="noopener">Launch the demo →</a></p>
<img class="hero" src="/images/work-task.png" alt="Purchase order calendar">
