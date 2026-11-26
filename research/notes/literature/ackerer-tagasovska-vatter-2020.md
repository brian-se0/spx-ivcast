---
aliases:
  - "Ackerer, Tagasovska and Vatter (2020)"
title: "Deep Smoothing of the Implied Volatility Surface"
authors:
  - "Damien Ackerer"
  - "Natasa Tagasovska"
  - "Thibault Vatter"
year: 2020
venue: "34th Conference on Neural Information Processing Systems (NeurIPS 2020); arXiv:1906.05065v3"
doi: ""
status: uncited
pdf: "[[lit_review/1906.05065v3.pdf]]"
pdf_version: preprint
asset_class: "S&P 500 index options and synthetic data"
sample_period: "January to April 2018 and September to December 2008 (S&P 500 data)"
forecast_object: "fit, interpolation and extrapolation of the implied volatility surface"
horizon: "not applicable"
methods:
  - "neural network with soft no-arbitrage penalties"
  - "neural correction on top of a standard model (SSVI prior)"
benchmarks:
  - "standard IVS models"
evaluation_design: "trained daily; separate training, interpolation and extrapolation test sets"
loss_metrics:
  - "RMSE"
  - "MAPE"
  - "arbitrage-violation losses"
headline_finding: "A penalized neural network yields essentially arbitrage-free surfaces and helps when data are sparse or erroneous."
tags:
  - literature
  - literature/surface-construction
  - literature/no-arbitrage
---

# Ackerer, Tagasovska and Vatter (2020)

**Deep Smoothing of the Implied Volatility Surface.** NeurIPS 2020 (arXiv:1906.05065v3).

## Question
- How can a neural network fit and predict an implied volatility surface while avoiding arbitrage?

## Data
- Synthetic surfaces and S&P 500 option prices (Jan-Apr 2018; Sep-Dec 2008).

## Method
- Network with a no-arbitrage penalty weight lambda, optionally correcting a classical model.

## Evaluation design
- Daily training; error on training points and on held-out interpolation and extrapolation points.

## Findings
- Lambda of 1 or 10 gives essentially arbitrage-free surfaces; lambda 0 does not.

## Limits and caveats
- Same-day cross-sectional fitting, not next-session forecasting; surface dynamics are left as an extension.

## Use in this study
Relates to surface construction and no-arbitrage smoothing rather than to forecasting the surface one session ahead.
