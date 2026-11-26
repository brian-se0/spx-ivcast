---
aliases:
  - "Stahl (2022)"
title: "Asymptotic extrapolation of model-free implied variance: exploring structural underestimation in the VIX Index"
authors:
  - "Philip Stahl"
year: 2022
venue: "Review of Derivatives Research"
doi: "10.1007/s11147-022-09190-2"
status: uncited
pdf: "[[lit_review/s11147-022-09190-2.pdf]]"
pdf_version: published
asset_class: "S&P 500 and DJIA index options (VIX-type indices)"
sample_period: "not stated"
forecast_object: "not a forecasting paper (truncation error in model-free implied variance)"
horizon: "not applicable"
methods:
  - "asymptotic behaviour of the volatility surface used for a tail correction term"
benchmarks:
  - "CBOE VIX methodology"
evaluation_design: "not applicable"
loss_metrics: []
headline_finding: "The VIX structurally underestimates model-free implied volatility because the smile is not extrapolated in the tails, and the error varies over time."
tags:
  - literature
  - literature/surface-construction
---

# Stahl (2022)

**Asymptotic extrapolation of model-free implied variance: exploring structural underestimation in the VIX Index.** Rev. Deriv. Res. 25: 315-339.

## Question
- How large is the error from omitting tail extrapolation of the volatility smile in VIX-style calculations?

## Data
- Reference data published by CBOE (near-term data) and sample data for the S&P 500 and DJIA indices.

## Method
- A model-independent correction term needing only option prices at the two outermost strikes.

## Evaluation design
- Not applicable.

## Findings
- Underestimation is larger in periods of sustained low volatility for the S&P 500 and DJIA, but not for the volatility-of-VIX index.

## Limits and caveats
- Not stated in the parts read.

## Use in this study
Relevant to tail treatment of the smile when summarising SPX option prices into volatility measures.
