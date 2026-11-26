---
aliases:
  - "Vuletic and Cont (2024)"
title: "VolGAN: A Generative Model for Arbitrage-Free Implied Volatility Surfaces"
authors:
  - "Milena Vuletić"
  - "Rama Cont"
year: 2024
venue: "Applied Mathematical Finance"
doi: "10.1080/1350486X.2025.2471317"
status: uncited
pdf: "[[lit_review/VolGAN  A Generative Model for Arbitrage-Free Implied Volatility Surfaces.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options (SPX)"
sample_period: "January 3, 2000 to February 28, 2023"
forecast_object: "joint dynamics of the SPX implied volatility surface and the underlying (one-day-ahead scenarios)"
horizon: "1 day"
methods:
  - "generative adversarial network with smoothness penalty"
  - "scenario re-weighting for static arbitrage"
benchmarks:
  - "classical GAN"
  - "Black-Scholes delta and delta-vega hedging"
evaluation_design: "chronological split: training 3 Jan 2000 to 16 Jun 2018, test 17 Jun 2019 to 28 Feb 2023"
loss_metrics:
  - "arbitrage penalty"
  - "principal-component comparison"
headline_finding: "VolGAN learns the covariance structure of SPX implied-volatility co-movements and generates realistic VIX dynamics."
tags:
  - literature
  - literature/surface-dynamics
  - literature/machine-learning
---

# Vuletic and Cont (2024)

**VolGAN: A Generative Model for Arbitrage-Free Implied Volatility Surfaces.** Applied Mathematical Finance 31(4): 203-238.

## Question
- Can a generative model produce realistic one-day-ahead joint scenarios for surface and underlying?

## Data
- OptionMetrics SPX surfaces on a moneyness-maturity grid; VIX from CBOE.

## Method
- GAN trained on surface and price time series, followed by arbitrage re-weighting.

## Evaluation design
- Out-of-sample test set; PCA of simulated versus market increments; simulated VIX.

## Findings
- Simulated principal components resemble the market's; data-driven hedges outperform delta and delta-vega.

## Limits and caveats
- Generates scenarios rather than a point forecast.

## Use in this study
Closest generative counterpart: a machine-learning model of next-day SPX surface dynamics that a referee may expect to see discussed alongside the point-forecast comparison.
