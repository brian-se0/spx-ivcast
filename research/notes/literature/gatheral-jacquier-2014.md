---
aliases:
  - "Gatheral and Jacquier (2014)"
title: "Arbitrage-free SVI volatility surfaces"
authors:
  - "Jim Gatheral"
  - "Antoine Jacquier"
year: 2014
venue: "Quantitative Finance"
doi: "10.1080/14697688.2013.819986"
status: cited
pdf: "[[lit_review/Arbitrage-free SVI volatility surfaces.pdf]]"
pdf_version: published
asset_class: "S&P 500 (SPX) index options"
sample_period: "single day: 15 September 2011"
forecast_object: "not a forecasting paper; parameterizes the total implied variance surface"
horizon: "not applicable"
methods:
  - "SVI slice parameterizations (raw, natural, SVI-JW)"
  - "SSVI (Surface SVI)"
  - "Slice-by-slice SVI calibration with a crossedness penalty"
benchmarks:
  - "Square-root SVI fit (initial guess)"
evaluation_design: "not applicable (one-day calibration example)"
loss_metrics:
  - "Sum of squared differences between fitted and mid option prices"
headline_finding: "SSVI is a closed-form class of SVI surfaces with explicit conditions that exclude calendar-spread and butterfly arbitrage."
tags:
  - literature
  - literature/no-arbitrage
  - literature/surface-construction
---

# Gatheral and Jacquier (2014)

**Arbitrage-free SVI volatility surfaces.** Quantitative Finance 14(1): 59-71.

## Question
- How can SVI be calibrated so that static arbitrage is guaranteed absent, and is there a closed-form class of arbitrage-free SVI surfaces?

## Data
- SPX option quotes at 3pm on 15 September 2011, all 14 expirations; one calibration example.

## Method
- Works in total implied variance w(k,t) = σ²(k,t)·t, with k the log-strike relative to the forward.
- A surface is free of static arbitrage when it has no calendar-spread arbitrage and no maturity slice has butterfly arbitrage.
- Introduces SSVI, a surface driven by at-the-money total variance θ, a correlation ρ and a function φ(θ).
- Calibration: square-root SVI initial fit, then slice-by-slice least squares on prices with a penalty for crossed slices.

## Evaluation design
- Not a forecast evaluation; fitted smiles are plotted against bid and offered implied volatilities.

## Findings
- With proportional dividends, calendar-spread arbitrage is absent if and only if w is non-decreasing in maturity at every k.
- A slice has no butterfly arbitrage if and only if a function g of w and its first two derivatives is non-negative, plus a large-strike limit condition.
- Raw SVI: no general parameter conditions excluding butterfly arbitrage are found.
- SSVI: necessary and sufficient conditions for no calendar-spread arbitrage (Theorem 4.1); sufficient conditions for no butterfly arbitrage (Theorem 4.2).

## Limits and caveats
- The SSVI butterfly conditions are sufficient, not necessary.
- One trading day, no numerical fit statistics; surface dynamics are left for future research.

## Use in this study
- [[paper#Introduction]]: part of the arbitrage-geometry literature that motivates working in total-variance space.
- [[paper#Literature Review]]: arbitrage-free SVI surfaces; calendar-spread versus butterfly arbitrage.
- [[paper#Models]]: total-variance arbitrage conditions behind forecasting total variance.
- [[paper#Models]]: reference for calling the neural model arbitrage-aware, not arbitrage-free.
