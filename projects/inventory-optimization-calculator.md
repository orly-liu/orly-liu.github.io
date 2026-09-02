---
layout: default
title: Downtime-Sensitive Inventory Optimization Calculator
---

## Downtime-Sensitive Inventory Optimization Calculator

[← Back to portfolio](/)

**Problem.** Reorder points for spare parts were set by rule of thumb. Standard
EOQ balances holding cost against ordering cost, but it says nothing about what
a stockout actually costs — and for a part that idles a crane, the cost of
being one unit short is not comparable to the cost of holding one unit too
many. Treating both the same systematically under-stocks the parts that matter
most.

**Approach.** Built the downtime cost into the stocking decision directly.
From unit price, holding rate, lead time, annual demand, ordering cost and
equipment downtime cost per day, the model works through:

- **Economic order quantity** — the classic cost-balancing order size
- **Expected demand during lead time** — the exposure window
- **Overstock and understock cost** — where downtime cost enters, as the real
  penalty for being short
- **Critical ratio** — understock over the sum of both, giving the service
  level the economics justify rather than one picked by policy
- **Poisson demand distribution** — the discrete distribution appropriate for
  slow-moving spares, where a normal approximation misreads the tail
- **Reorder point and maximum stock** — the actual output, compared against
  current on-hand so the recommendation is a decision, not a number

**Result.** Reorder points and stock levels that reflect what a stockout costs.
Validated against @RISK Monte Carlo simulation, with a 2.44% deviation between
the closed-form recommendation and the simulated optimum.

**Stack.** A single self-contained HTML file, no dependencies and no install.
Runs entirely in the browser, keeps a calculation history so scenarios can be
compared side by side, and has a dark mode for warehouse floor screens.

> **About the inputs.** The default values are illustrative rather than drawn
> from any real part. Enter your own figures — the tool holds no embedded data.

<p><a class="launch" href="/demos/downtime-sensitive-inventory-optimization-calculator-anonymized.html" target="_blank" rel="noopener">Launch the demo →</a></p>
