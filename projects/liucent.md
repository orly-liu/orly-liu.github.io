---
layout: default
title: Liucent — Interactive Purchase Order Calendar
---

## Liucent — Interactive Purchase Order Calendar

[← Back to portfolio](/)

**Problem.** Tracking open purchase requisitions meant re-running the same ERP report and reading a flat list of order lines. Nothing showed what was arriving in a given week, and urgent lines sat buried among routine ones. Anyone needing a status update had to chase a buyer or inventory manager and wait for them to search the ERP by hand, and the same question got answered over and over by the few people with access.

**Approach.** Rebuilt the report as a week calendar. Order lines are grouped by
purchase order and placed on their planned delivery date, ranked by delivery
code so urgent lines surface first. Filters cover department, order status, and
cost center. Loading a new export matches columns by header name, and a preview
screen flags anomalies.

**Result.** Replaced manual requisition tracking. Open orders are
readable at a glance, and the buyer chasing a delivery can see which orders are
urgent, which are already received, and which have no confirmed date.

**Stack.** Vanilla JavaScript with no dependencies. Custom CSV parser with
delimiter detection and fuzzy header matching, the File System Access API so an
updated copy can overwrite the original in place, and a self-contained export
that splices the current data back into the HTML.

> **About the data.** This demo runs on generated data. Order numbers, part
> numbers, suppliers, prices, cost centres and people are synthetic — only the
> structure and statistical shape of the original are preserved.

<p><a class="launch" href="/demos/liucent-anonymized.html" target="_blank" rel="noopener">Launch the demo →</a></p>
<img class="hero" src="/images/liucent.png" alt="Purchase order calendar">
