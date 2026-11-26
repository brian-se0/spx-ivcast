---
aliases:
  - "Radchenko, Vasnev and Wang (2020)"
title: "Too similar to combine? On negative weights in forecast combination"
authors:
  - "Peter Radchenko"
  - "Andrey L. Vasnev"
  - "Wendun Wang"
year: 2020
venue: "SSRN working paper"
doi: ""
status: uncited
pdf: "[[lit_review/ssrn-3647603.pdf]]"
pdf_version: preprint
asset_class: "not applicable (macroeconomic survey forecasts)"
sample_period: "Q4 1999 to Q2 2018"
forecast_object: "inflation, GDP growth and unemployment forecasts (European Central Bank Survey of Professional Forecasters)"
horizon: "not stated"
methods:
  - "forecast combination with an optimal trimming threshold for negative weights"
benchmarks:
  - "equal-weight combination"
evaluation_design: "expanding windows from Q2 2014; 16-quarter testing period"
loss_metrics:
  - "relative mean squared forecast error"
headline_finding: "Negative weights arise when highly correlated forecasts with similar variances are combined, and optimal trimming improves on the equal-weight benchmark by 5-10% (inflation), 15-30% (GDP) and over 30% (unemployment)."
tags:
  - literature
  - literature/forecast-combination
---

# Radchenko, Vasnev and Wang (2020)

**Too similar to combine? On negative weights in forecast combination.** SSRN working paper (July 2020 version).

## Question
- Why do negative weights appear in forecast combination, and should they be trimmed to zero?

## Data
- ECB Survey of Professional Forecasters, Q4 1999 to Q2 2018; forecasters with fewer than 24 responses removed.

## Method
- Analysis of the weights' variance, an optimal trimming threshold and simulations.

## Evaluation design
- Expanding windows, 16 quarters tested, relative MSFE.

## Findings
- Zero is an arbitrary threshold; the new strategy performs exceptionally well.

## Limits and caveats
- Macro survey data only.

## Use in this study
Relevant to combining forecasts from correlated models (ridge, elastic net, tree and neural models) should the study consider combinations.
