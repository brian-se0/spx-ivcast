---
aliases:
  - "Arratia, El Daou, Kagerhuber, and Smolyarova (2026)"
  - "Arratia et al. (2026)"
title: "Examining Challenges in Implied Volatility Forecasting: A Critical Review of Data Leakage and Feature Engineering combined with High-Complexity Models"
authors:
  - "Argimiro Arratia"
  - "Mahmoud El Daou"
  - "Jan Kagerhuber"
  - "Yulia Smolyarova"
year: 2026
venue: "Computational Economics"
doi: "10.1007/s10614-025-11172-z"
status: cited
pdf: "[[lit_review/s10614-025-11172-z.pdf]]"
pdf_version: published
asset_class: "Call options from OptionsDX option chains; underlying not named explicitly"
sample_period: "2010-2018, plus an additional test set of later days"
forecast_object: "One-day change in the implied volatility of individual options (also its log difference and its sign)"
horizon: "1 day"
methods:
  - "Feedforward neural network"
  - "XGBoost"
benchmarks:
  - "Hull and White (2017) minimum-variance-delta formula"
evaluation_design: "Shuffled 70/20/10 split replicated, then a chronological split keeping all options of a day in one set, plus an additional unseen test set"
loss_metrics:
  - "MSE"
  - "Gain over benchmark"
  - "R-squared"
  - "Weighted accuracy"
headline_finding: "The large gains of neural networks over the Hull-White formula come from leakage created by shuffled splits; under a chronological split no model gains more than 1.5% in MSE."
tags:
  - literature
  - literature/evaluation
  - literature/machine-learning
---

# Arratia, El Daou, Kagerhuber, and Smolyarova (2026)

**Examining Challenges in Implied Volatility Forecasting: A Critical Review of Data Leakage and Feature Engineering combined with High-Complexity Models.** Computational Economics, online-first article (received 22 December 2024; accepted 28 October 2025); volume, issue and pages are not printed in this PDF.

## Question

- Do the gains reported for the Cao, Chen, and Hull (2020) neural network over the Hull-White formula survive a leak-free split, and are MSE and gain suitable measures?

## Data

- OptionsDX option chains, 2010-2018; about 427,000 observations after cleaning (calls only, more than 14 days to expiry, delta between 0.05 and 0.95).
- Target: daily change in each option's implied volatility. Features: lagged delta, days to expiry, S&P 500 return (SPY_ret), and VIX.

## Method

- Feedforward networks (three layers of 80 neurons) and XGBoost with 2, 3 or 4 features, against the Hull-White formula.
- Later variants use the log difference of IV or its sign as the target.

## Evaluation design

- Shuffled 70/20/10 split first, then a chronological split that keeps all options of a day in one set; both are also scored on unseen later days.

## Findings

- Shuffled split: the 4-feature network has a gain of 0.4575 and 4-feature XGBoost 0.6638; on unseen days all six models lose to the benchmark (gains -0.0669 to -0.5247).
- Chronological split: gains over the benchmark do not exceed 1.5%.
- Same-day options share the index return and VIX, so shuffling lets models learn the date.
- Weighted accuracy: 0.6191 for the best model (4-feature XGBoost, binary target), 0.55942 for Hull-White.

## Limits and caveats

- The authors note that other forms of leakage may remain and that generalisation to live trading is uncertain.
- MSE on absolute IV changes overweights high-IV options and can score a right-direction forecast worse than a wrong-direction one.

## Use in this study

- [[paper#Literature Review]]: example of implied-volatility forecasting outside the full-surface setting that tests machine-learning models against a parametric benchmark.
- [[paper#Literature Review]]: evidence that randomized time-series splits create leakage and that familiar performance measures can mislead depending on how the target is built.
