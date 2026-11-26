---
aliases:
  - "Cont and Vuletic (2023)"
title: "Simulation of Arbitrage-Free Implied Volatility Surfaces"
authors:
  - "Rama Cont"
  - "Milena Vuletić"
year: 2023
venue: "Applied Mathematical Finance"
doi: "10.1080/1350486X.2023.2277960"
status: uncited
pdf: "[[lit_review/Simulation of Arbitrage-Free Implied Volatility Surfaces.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options (SPX)"
sample_period: "2000-2021"
forecast_object: "dynamic scenarios for the SPX implied volatility surface"
horizon: "not stated"
methods:
  - "principal component analysis of daily log implied-volatility changes"
  - "scenario re-weighting for static arbitrage constraints"
benchmarks: []
evaluation_design: "not stated"
loss_metrics: []
headline_finding: "Four principal components of daily SPX log implied-volatility changes explain over 90% of variance and support arbitrage-free simulation."
tags:
  - literature
  - literature/surface-dynamics
  - literature/no-arbitrage
---

# Cont and Vuletic (2023)

**Simulation of Arbitrage-Free Implied Volatility Surfaces.** Applied Mathematical Finance 30(2): 94-121.

## Question
- How can arbitrage-free surfaces be simulated while keeping realistic implied-volatility co-movements?

## Data
- OptionMetrics SPX implied volatility surface file, 2000-2021.

## Method
- PCA of daily changes in log implied volatility; a tractable arbitrage-free simulation method.

## Evaluation design
- Not stated in the parts read.

## Findings
- Four significant components read as level, skew, term structure and curvature.

## Limits and caveats
- Scenario generation, not point forecasting.

## Use in this study
Documents factor structure in daily SPX surface changes and no-arbitrage scenario generation, a distribution-oriented counterpart to the point forecasts compared here.
