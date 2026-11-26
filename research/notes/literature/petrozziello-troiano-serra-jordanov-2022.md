---
aliases:
  - "Petrozziello et al. (2022)"
title: "Deep learning for volatility forecasting in asset management"
authors:
  - "Alessio Petrozziello"
  - "Luigi Troiano"
  - "Angela Serra"
  - "Ivan Jordanov"
  - "Giuseppe Storti"
  - "Roberto Tagliaferri"
  - "Michele La Rocca"
year: 2022
venue: "Soft Computing"
doi: "10.1007/s00500-022-07161-1"
status: uncited
pdf: "[[lit_review/s00500-022-07161-1.pdf]]"
pdf_version: published
asset_class: "28 Dow Jones constituents plus SPY; 92 NASDAQ 100 stocks"
sample_period: "Dow Jones plus SPY January 2002 to August 2008; NASDAQ 100 December 2012 to November 2017"
forecast_object: "daily stock market volatility"
horizon: "daily"
methods:
  - "deep LSTM neural network"
benchmarks:
  - "R-GARCH"
  - "GJR-MEM"
evaluation_design: "rolling forecast from day 301 onward"
loss_metrics:
  - "MSE"
  - "QLIKE"
headline_finding: "The LSTM beats R-GARCH and GJR-MEM in high-volatility conditions and is comparable in tranquil periods."
tags:
  - literature
  - literature/volatility-forecasting
  - literature/machine-learning
---

# Petrozziello et al. (2022)

**Deep learning for volatility forecasting in asset management.** Soft Comput. 26: 8553-8574.

## Question
- Is a deep LSTM profitable for forecasting daily stock volatility versus parametric benchmarks?

## Data
- Two panels: DJIA constituents plus SPY (2002-2008) and NASDAQ 100 (2012-2017).

## Method
- Panel LSTM compared with univariate R-GARCH and GJR-MEM.

## Evaluation design
- Rolling forecasts from day 301, assessed with rolling-window MSE and QLIKE.

## Findings
- LSTM superior in high volatility, comparable in calm periods.

## Limits and caveats
- Return volatility, not implied volatility.

## Use in this study
Neural network versus parametric volatility forecasting with QLIKE; adjacent to, but not about, the implied-volatility surface.
