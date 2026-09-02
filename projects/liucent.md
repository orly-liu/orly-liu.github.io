---
layout: default
title: Liucent — Interactive Purchase Order Calendar
---

## Liucent — Interactive Purchase Order Calendar

[← Back to portfolio](/)

**Problem.** Tracking open purchase requisitions meant re-running the same ERP
report and reading a flat list of order lines. Nothing showed what was arriving
in a given week, and urgent lines sat buried among routine ones — so chasing a
late delivery started with manually sorting a spreadsheet.

**Approach.** Rebuilt the report as a week calendar. Order lines are grouped by
purchase order and placed on their planned delivery date, ranked by delivery
code so urgent lines surface first. Filters cover department, order status and
cost centre, and a toggle switches the calendar between planned delivery date
and creation date. Loading a new export is a drag-and-drop: columns are matched
by header name rather than position, and a preview screen flags anomalies —
shifted header rows, unrecognised status codes, unmapped cost centres — before
anything is committed.

**Result.** Replaced manual requisition tracking. Open orders for a week are
readable at a glance, and the buyer chasing a delivery can see which orders are
urgent, which are already received, and which have no confirmed date.

**Stack.** Vanilla JavaScript with no dependencies. Custom CSV parser with
delimiter detection and fuzzy header matching, the File System Access API so an
updated copy can overwrite the original in place, and a self-contained export
that splices the current data and department mapping back into the HTML — so
the file that gets emailed is the whole application.

**Portability.** Cost centre numbering differs between terminals, so the
department-to-cost-centre mapping is editable in the interface rather than
hard-coded. Assignments are validated (a code can belong to only one
department) and are written into the exported file, so a colleague at another
site can remap it once and keep their own version.

> **About the data.** This demo runs on generated data. Order numbers, part
> numbers, suppliers, prices, cost centres and people are synthetic — only the
> structure and statistical shape of the original are preserved.

<p><a class="launch" href="/demos/liucent-anonymized.html" target="_blank" rel="noopener">Launch the demo →</a></p>
<img class="hero" src="/images/liucent.png" alt="Purchase order calendar">
