---
aliases:
  - "Maciak and Vitali (2024)"
title: "Using interpolated implied volatility for analysing exogenous market changes"
authors:
  - "Matúš Maciak"
  - "Sebastiano Vitali"
year: 2024
venue: "Computational Management Science"
doi: "10.1007/s10287-024-00505-2"
status: uncited
pdf: "[[lit_review/s10287-024-00505-2.pdf]]"
pdf_version: published
asset_class: "Erste Group call options on EUREX Deutschland (Datastream implied volatilities)"
sample_period: "50 trading days, 16 July 2018 to 21 September 2018"
forecast_object: "not a forecasting paper (detection of exogenous changepoints in implied volatility)"
horizon: "constant time to maturity"
methods:
  - "artificial constant-maturity options from interpolated volatilities"
  - "changepoint tests on panel data"
benchmarks:
  - "standard implied volatility"
evaluation_design: "not applicable"
loss_metrics: []
headline_finding: "Interpolated constant-maturity volatilities remove instability from natural market dynamics while preserving exogenous changes, enabling formal tests."
tags:
  - literature
  - literature/surface-construction
---

# Maciak and Vitali (2024)

**Using interpolated implied volatility for analysing exogenous market changes.** Comput. Manag. Sci. 21: 25.

## Question
- How can exogenous market changes be separated from endogenous implied-volatility movements?

## Data
- Erste Group call implied volatilities, 50 trading days in 2018.

## Method
- Artificial options with constant time to maturity built by interpolation; statistical tests for changepoints in panels.

## Evaluation design
- Statistical theory, empirical comparisons and a real-data illustration.

## Findings
- Standard implied volatility is insufficient for this purpose; the interpolated version works.

## Limits and caveats
- Single-stock illustration.

## Use in this study
Relevant to constant-maturity interpolation of implied volatilities, which fixed-grid surface forecasting also requires.
