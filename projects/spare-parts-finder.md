---
layout: default
title: LAX Spare Parts Finder
---

## LAX Spare Parts Finder

[← Back to portfolio](/)

**Problem.** Locating a spare part meant querying the ERP across several
screens for roughly 10 minutes per lookup, several times a shift.

**Approach.** Consolidated the local inventory extract and the global-wide
manufacturer-part-number extract into a single-file browser tool. No server or
installation required; one HTML file anyone can open or email.

**Result.** Inventory lookup time under 1 minute. Staff can check whether a part is available
at another terminal before raising a purchase requisition.

**Stack.** Vanilla JavaScript, SheetJS for spreadsheet parsing, a Web Worker
so a 200,000-row import doesn't freeze the page, and an embedded JSON payload
so the file works offline.

> **About the data.** This demo runs on generated data. Part numbers,
> suppliers, costs, terminals, and people are synthetic — only the structure
> and statistical shape of the original are preserved.

<p><a class="launch" href="/demos/spare-parts-finder-anonymized.html" target="_blank" rel="noopener">Launch the demo →</a></p>
<img class="hero" src="/images/spare-parts.png" alt="Purchase order calendar">
