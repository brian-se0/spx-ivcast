---
aliases:
  - "Francois, Galarneau-Vincent, Gauthier and Godin (2022)"
title: "Venturing into uncharted territory: An extensible implied volatility surface model"
authors:
  - "Pascal François"
  - "Rémi Galarneau-Vincent"
  - "Geneviève Gauthier"
  - "Frédéric Godin"
year: 2022
venue: "Journal of Futures Markets"
doi: "10.1002/fut.22364"
status: uncited
pdf: "[[lit_review/Venturing into uncharted territory_ An extensible implied volatility surface model.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options (SPX)"
sample_period: "January 1996 to December 2019"
forecast_object: "factor-based representation (smoothing, interpolation, extrapolation) of the IV surface"
horizon: "not applicable"
methods:
  - "parametric factor model with slope, smile attenuation and smirk factors"
benchmarks:
  - "Heston"
  - "Goncalves and Guidolin"
  - "Chalamandaris and Tsekrekos"
evaluation_design: "calibration fit; arbitrage checks with butterfly and calendar spreads"
loss_metrics: []
headline_finding: "A twice differentiable factor specification fits SPX surfaces better than the benchmarks and extrapolates well."
tags:
  - literature
  - literature/surface-construction
---

# Francois, Galarneau-Vincent, Gauthier and Godin (2022)

**Venturing into uncharted territory: An extensible implied volatility surface model.** Journal of Futures Markets 42: 1912-1940.

## Question
- Can a factor-based IV function capture surface stylized facts and extrapolate beyond quoted options?

## Data
- SPX option IV surface, January 1996 to December 2019.

## Method
- Factors for moneyness and maturity slopes, smile attenuation and the smirk.

## Evaluation design
- Calibration performance versus benchmarks; static-arbitrage tests.

## Findings
- Passes the arbitrage tests; supports risk-neutral density and Greeks extraction.

## Limits and caveats
- Fits each day's surface; no out-of-sample forecasting of future surfaces is described in the pages read.

## Use in this study
Relates to parametric factor descriptions of the SPX surface that could define the targets of a factor-based forecast.
