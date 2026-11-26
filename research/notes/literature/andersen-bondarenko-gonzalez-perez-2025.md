---
aliases:
  - "Andersen, Bondarenko and Gonzalez-Perez (2025)"
title: "VIX maturity interpolation"
authors:
  - "Torben G. Andersen"
  - "Oleg Bondarenko"
  - "Maria T. Gonzalez-Perez"
year: 2025
venue: "Review of Derivatives Research"
doi: "10.1007/s11147-025-09210-x"
status: uncited
pdf: "[[lit_review/s11147-025-09210-x.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options (VIX)"
sample_period: "weekly and monthly options from March 2012 to December 2020; one sample covers May 2012 to December 2023"
forecast_object: "not a forecasting paper (VIX maturity interpolation error)"
horizon: "30-day VIX; also a 9-day VIX"
methods:
  - "historical simulation of interpolation errors using weekly option quotes"
benchmarks:
  - "two alternative interpolation schemes based on monthly options"
evaluation_design: "not applicable"
loss_metrics:
  - "absolute deviation from the weekly-option VIX measure"
headline_finding: "Including weekly options in 2014 cut average interpolation error about tenfold, and the old-to-new VIX gap is a good proxy for the error."
tags:
  - literature
  - literature/surface-construction
---

# Andersen, Bondarenko and Gonzalez-Perez (2025)

**VIX maturity interpolation.** Rev. Deriv. Res. 28: 4.

## Question
- How large are the errors from interpolating two model-free variance measures to a constant 30-day maturity, and where do they come from?

## Data
- Cboe data on monthly and weekly options from 2012; the new VIX is not backdated, so the series differs before and after 2014.

## Method
- Historical simulation across tenors and maturity cycles.

## Evaluation design
- Not applicable.

## Findings
- Errors were sizable under stress before 2014; alternative interpolation schemes reduce average errors but are not uniformly superior; errors amplify for shorter-horizon indices.

## Limits and caveats
- Monthly-option-only indices elsewhere still face the problem.

## Use in this study
Relevant to constant-maturity interpolation along the maturity axis of SPX option data.
