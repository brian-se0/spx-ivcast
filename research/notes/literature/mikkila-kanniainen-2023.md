---
aliases:
  - "Mikkila and Kanniainen (2023)"
title: "Empirical deep hedging"
authors:
  - "Oskari Mikkilä"
  - "Juho Kanniainen"
year: 2023
venue: "Quantitative Finance"
doi: "10.1080/14697688.2022.2136037"
status: uncited
pdf: "[[lit_review/Empirical deep hedging.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options"
sample_period: "January 3, 2006 to December 31, 2013 (intraday)"
forecast_object: "not a forecasting paper (hedging policy)"
horizon: "60-minute rebalancing within 5-trading-day hedging periods"
methods:
  - "deep reinforcement learning with continuous actions"
benchmarks:
  - "Black-Scholes delta hedging"
evaluation_design: "training 2006-2011, validation 2012, independent test data"
loss_metrics:
  - "hedging P&L with risk-return reward"
headline_finding: "An agent trained directly on intraday S&P 500 data beats one trained on synthetic stochastic-volatility data and Black-Scholes delta hedging."
tags:
  - literature
  - literature/hedging
  - literature/machine-learning
---

# Mikkila and Kanniainen (2023)

**Empirical deep hedging.** Quantitative Finance 23(1): 111-122.

## Question
- Can a hedging agent learn purely from empirical option data, without volatility or jump model assumptions?

## Data
- CBOE Livevol minute-level S&P 500 options, used hourly.

## Method
- Deep reinforcement learning with transaction costs of 1 bp.

## Evaluation design
- Chronological training, validation and test sets.

## Findings
- Empirically trained agents outperform synthetic-data agents.

## Limits and caveats
- Targets hedging, not surface forecasts.

## Use in this study
Not directly related.
