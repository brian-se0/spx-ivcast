---
aliases:
  - "Li, Kang and Li (2022)"
title: "Bayesian forecast combination using time-varying features"
authors:
  - "Li Li"
  - "Yanfei Kang"
  - "Feng Li"
year: 2022
venue: "arXiv:2108.02082v3 [econ.EM]"
doi: ""
status: uncited
pdf: "[[lit_review/2108.02082v3.pdf]]"
pdf_version: preprint
asset_class: "S&P 500 index returns; M3 competition series"
sample_period: "S&P 500 daily returns January 4, 2010 to September 18, 2019"
forecast_object: "density and point forecast combination weights (return volatility)"
horizon: "not stated"
methods:
  - "feature-based Bayesian forecast combination with Bayesian variable selection"
benchmarks:
  - "SA"
  - "OP"
  - "GP"
  - "GARCH(1,1)"
  - "realized GARCH(1,1)"
  - "stochastic volatility"
evaluation_design: "in-sample and out-of-sample; sliding window features"
loss_metrics:
  - "log predictive score"
headline_finding: "Time-varying, feature-based weights give higher log scores than the benchmark combination schemes."
tags:
  - literature
  - literature/forecast-combination
---

# Li, Kang and Li (2022)

**Bayesian forecast combination using time-varying features.** arXiv:2108.02082v3.

## Question
- Can time-varying weights built from series features improve density forecast combination?

## Data
- S&P 500 daily percent log returns (Jan 4, 2010 to Sep 18, 2019) and M3 competition data.

## Method
- Weights from Bayesian log predictive scores; Bayesian variable selection picks features.

## Evaluation design
- Combines pairs and triples of GARCH, realized GARCH and SV; DM tests against the best benchmark.

## Findings
- The proposed scheme has the highest in-sample log score in all combinations.

## Limits and caveats
- Return volatility of one index, not implied-volatility surfaces.

## Use in this study
Relates to forecast combination as an alternative to picking a single model, though it is not applied to implied-volatility surfaces.
