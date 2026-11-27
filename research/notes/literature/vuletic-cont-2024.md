---
aliases:
  - "Vuletić and Cont (2024)"
  - "Vuletic and Cont (2024)"
title: "VolGAN: A Generative Model for Arbitrage-Free Implied Volatility Surfaces"
authors:
  - "Milena Vuletić"
  - "Rama Cont"
year: 2024
venue: "Applied Mathematical Finance"
doi: "10.1080/1350486X.2025.2471317"
status: cited
pdf: "[[lit_review/VolGAN  A Generative Model for Arbitrage-Free Implied Volatility Surfaces.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options (SPX)"
sample_period: "3 January 2000 to 28 February 2023"
forecast_object: "one-day-ahead joint scenarios for the SPX log-return and the increment of the log implied-volatility surface"
horizon: "1 day"
methods:
  - "conditional generative adversarial network with a smoothness penalty"
  - "scenario re-weighting by a static-arbitrage penalty"
  - "scenario-based regression hedging with LASSO instrument selection"
benchmarks:
  - "GAN trained with binary cross-entropy only"
  - "VolGAN without re-weighting"
  - "Black-Scholes delta hedging"
  - "Black-Scholes delta-vega hedging"
evaluation_design: "single chronological split: training 3 Jan 2000 to 16 Jun 2018, test 17 Jun 2019 to 28 Feb 2023"
loss_metrics:
  - "arbitrage penalty"
  - "quantile exceedance ratios"
  - "principal-component variance shares and eigenvector inner products"
  - "hedging tracking error and Value-at-Risk"
headline_finding: "A conditional GAN with a smoothness penalty reproduces the level, skew and curvature structure of daily SPX surface changes out of sample, and its scenario-based hedges of a straddle outperform Black-Scholes delta and delta-vega hedges."
tags:
  - literature
  - literature/surface-dynamics
  - literature/machine-learning
---

# Vuletić and Cont (2024)

**VolGAN: A Generative Model for Arbitrage-Free Implied Volatility Surfaces.** Applied Mathematical Finance 31(4): 203-238.

## Question
- Can a data-driven generative model simulate realistic one-day-ahead joint scenarios for the surface and the underlying while respecting static-arbitrage constraints?

## Data
- OptionMetrics Option Prices file for SPX, 3 January 2000 to 28 February 2023; VIX closes from CBOE.
- Surfaces come from vega-weighted kernel smoothing on 11 moneyness values (K/S 0.6 to 1.4) and maturities from one day to one year.

## Method
- A conditional GAN takes the previous log surface, two lagged index returns and one-month realized volatility, and generates the next-day index return and log-surface increment.
- The generator loss adds smoothness penalties in moneyness and maturity to binary cross-entropy; the arbitrage penalty is left out of the loss.
- Outputs are not guaranteed to satisfy static arbitrage, so the 10,000 generated scenarios are re-weighted by exp(-β × penalty), following Cont and Vuletić (2023).

## Evaluation design
- Training 3 Jan 2000 to 16 Jun 2018; test 17 Jun 2019 to 28 Feb 2023. The text also describes the out-of-sample results as four and a half years after training.
- Scenario properties are assessed (arbitrage penalties, quantile exceedance, PCA, correlations, simulated VIX, straddle hedging). Conditional-mean next-day forecasts are plotted with 95% intervals but not scored against a no-change or other forecasting benchmark.

## Findings
- Mean test-set arbitrage penalty: market data 0.0096, binary-cross-entropy GAN 2.4635, raw VolGAN 0.0199, re-weighted VolGAN 0.0127.
- The top three components explain 51.25%, 34.00% and 5.01% of test-data variance against 45.31%, 25.69% and 12.76% in simulations.
- 49.61% of 3-month at-the-money realizations fall below the re-weighted 97.5% quantile (64.51% without re-weighting); dropping the re-weighting improves forecasts in turbulent periods and improves hedging.
- Straddle tracking-error standard deviation: 5.766 and 4.940 for two VolGAN hedges, 6.755 for delta, 28.307 for delta-vega.

## Limits and caveats
- The authors do not expect outputs to be completely arbitrage-free, because the input surfaces may themselves admit static arbitrage.
- No point-forecast error metric is reported.

## Use in this study

- [[paper#Literature Review]]: cited as a generative approach that produces one-day-ahead joint scenarios for the index return and the surface, assessed on scenario properties and hedging rather than on point-forecast accuracy against a no-change benchmark, with static arbitrage handled by penalty-based re-weighting and no guarantee that outputs satisfy the constraints.
