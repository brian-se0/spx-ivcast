---
aliases:
  - "Cont and Vuletić (2023)"
  - "Cont and Vuletic (2023)"
title: "Simulation of Arbitrage-Free Implied Volatility Surfaces"
authors:
  - "Rama Cont"
  - "Milena Vuletić"
year: 2023
venue: "Applied Mathematical Finance"
doi: "10.1080/1350486X.2023.2277960"
status: cited
pdf: "[[lit_review/Simulation of Arbitrage-Free Implied Volatility Surfaces.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options (SPX)"
sample_period: "2000-2021"
forecast_object: "not a forecasting paper; simulated joint paths of the SPX implied-volatility surface and the index"
horizon: "not applicable"
methods:
  - "principal component analysis of daily changes in log implied volatility"
  - "factor model with independent Ornstein-Uhlenbeck factors"
  - "static-arbitrage penalty on relative call prices over a finite grid"
  - "Weighted Monte Carlo scenario re-weighting"
benchmarks: []
evaluation_design: "in-sample description and simulation; no out-of-sample forecast evaluation"
loss_metrics:
  - "arbitrage penalty quantiles"
  - "relative entropy of re-weighted scenarios"
headline_finding: "Four principal components explain over 90% of the variance of daily SPX log implied-volatility changes, and re-weighting simulated factor-model paths by an arbitrage penalty removes static arbitrage as the penalty parameter grows."
tags:
  - literature
  - literature/surface-dynamics
  - literature/no-arbitrage
---

# Cont and Vuletić (2023)

**Simulation of Arbitrage-Free Implied Volatility Surfaces.** Applied Mathematical Finance 30(2): 94-121.

## Question
- How can a realistic model of implied-volatility co-movements be made to generate surfaces free of static arbitrage?

## Data
- OptionMetrics SPX Implied Volatility Surface File, daily, 2000-2021, interpolated to 10 moneyness values (K/S 0.6 to 1.4) by 8 maturities (30 to 365 calendar days).
- 80.2% of these vendor surfaces carry a zero arbitrage penalty; the largest spikes fall on 29/09/2008 and 13/03/2020.

## Method
- PCA of daily changes in log implied volatility, keeping components whose correlation-matrix eigenvalue exceeds the Marčenko-Pastur threshold.
- Baseline model: the mean surface scaled by the exponential of four principal components weighted by independent Ornstein-Uhlenbeck factors, with a correlated index diffusion.
- Arbitrage penalty: summed positive parts of the calendar-spread, call-spread and butterfly inequalities on relative call prices over the grid; zero exactly when the gridded surface admits no static arbitrage.
- Each simulated path is re-sampled with weight proportional to exp(-β × path penalty), so 1/β acts as an arbitrage tolerance and only penalty-free paths survive as β grows.

## Evaluation design
- No forecast evaluation and no train/test split: arbitrage-penalty quantiles and relative entropy across β for 100,000 simulated 3-month paths, plus simulated 10-year VIX and SPX paths.

## Findings
- Four eigenvalues clear the threshold; the first four components explain over 90% of variance (68.88% for the first) and read as level, skew, term structure and curvature.
- Factor processes are highly positively autocorrelated and mean-revert over several months, consistent with AR(1)/Ornstein-Uhlenbeck dynamics.
- In the SPX factor model 62.761% of paths and 16.055% of surfaces carry a non-zero penalty before re-weighting; arbitrage is effectively removed for β above 10^4.

## Limits and caveats
- Freedom from arbitrage is defined on a finite grid and reached as β becomes large; it is not built into the factor model.
- Factor persistence is documented, but predictive accuracy is not measured.

## Use in this study

- [[paper#Literature Review]]: cited for SPX surfaces from 2000 to 2021, where four principal components explain over 90% of the variance of daily changes in log implied volatility and the factor processes are highly autocorrelated and mean-reverting over several months.
- [[paper#Literature Review]]: cited for the finding that about one in five daily surfaces in a vendor file of interpolated SPX implied volatilities violates static no-arbitrage conditions.
