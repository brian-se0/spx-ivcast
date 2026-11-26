---
aliases:
  - "Hull and White (2017)"
title: "Optimal delta hedging for options"
authors:
  - "John Hull"
  - "Alan White"
year: 2017
venue: "Journal of Banking and Finance"
doi: "10.1016/j.jbankfin.2017.05.006"
status: uncited
pdf: "[[lit_review/1-s2.0-S0378426617301085-main.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options (also S&P 100, Dow Jones, individual stocks, commodity and interest-rate ETFs)"
sample_period: "out-of-sample tests January 2007 to August 2015 for the S&P 500"
forecast_object: "expected change in implied volatility conditional on an asset price change (minimum variance delta)"
horizon: "1 day"
methods:
  - "empirical model for the minimum variance delta"
benchmarks:
  - "practitioner Black-Scholes delta"
  - "SABR"
  - "local volatility"
evaluation_design: "out-of-sample; parameters estimated on a 36-month window and applied each day of the next month"
loss_metrics:
  - "average hedging gain"
headline_finding: "An empirical minimum variance delta improves hedging over stochastic volatility models calibrated afresh each day."
tags:
  - literature
  - literature/hedging
---

# Hull and White (2017)

**Optimal delta hedging for options.** Journal of Banking and Finance 82: 180-190.

## Question
- Can the price/volatility correlation be used to build a delta that minimizes the variance of option-position changes?

## Data
- OptionMetrics daily option and underlying data; S&P 500 options plus other indices, stocks and ETFs.

## Method
- Fits an empirical model for the derivative of expected implied volatility with respect to the asset price.

## Evaluation design
- Out-of-sample hedging tests; the SABR and local volatility models are recalibrated daily per maturity.

## Findings
- The empirical rule beats the stochastic volatility benchmarks; minimum variance delta is below the practitioner delta for equities.

## Limits and caveats
- Hedging gain is not a surface-forecast metric; it targets delta, not surface levels.

## Use in this study
Not directly related.
