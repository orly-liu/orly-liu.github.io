---
layout: default
title: Downtime-Sensitive Inventory Optimization Calculator
---

## Downtime-Sensitive Inventory Optimization Calculator

[← Back to portfolio](/)

**Problem.** Reorder points for spare parts were set by rule of thumb. 
Traditional criticality matrix relies on qualitative labels, sorts parts into
high, medium, and low bands, and applies a blanket service level to each. 
Standard EOQ balances holding cost against ordering cost, but it says nothing 
about what a stockout actually costs


**Approach.** Built the downtime cost into the stocking decision directly.
From unit price, holding rate, lead time, annual demand, ordering cost and
equipment downtime cost per day, the model works through:

- **Economic order quantity** — the classic cost-balancing order size
- **Expected demand during lead time** — the exposure window
- **Overstock and understock cost** — penalty for holding one additional or
  one less unit
- **Critical ratio** — compares the cost of understocking with the combined
  costs of understocking and overstocking, giving the service level the
  economics justify
- **Poisson demand distribution** — the cumulative probability measures the
   likelihood that actual lead-time demand will be less than or equal to a
  candidate stocking quantity (k).
- **Reorder point and maximum stock** — the actual output, compared against
  current on-hand

**Result.** Reorder points and stock levels that reflect what a stockout costs.
Validated against @RISK Monte Carlo simulation, with a 2.44% deviation between
the closed-form recommendation and the simulated optimum.

> **About the inputs.** The default values are illustrative rather than drawn
> from any real part. Enter your own figures — the tool holds no embedded data.

<p><a class="launch" href="/demos/downtime-sensitive-inventory-optimization-calculator-anonymized.html" target="_blank" rel="noopener">Launch the demo →</a></p>
<img class="hero" src="/images/calculator.png" alt="Purchase order calendar">
