---
aliases:
  - "Chen, Grith, and Lai (2026)"
title: "Neural Tangent Kernel in Implied Volatility Forecasting: A Nonlinear Functional Autoregression Approach"
authors:
  - "Ying Chen"
  - "Maria Grith"
  - "Hannah L. H. Lai"
year: 2026
venue: "Journal of Business & Economic Statistics"
doi: "10.1080/07350015.2025.2489087"
status: cited
pdf: "[[lit_review/Neural Tangent Kernel in Implied Volatility Forecasting  A Nonlinear Functional Autoregression Approach.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options"
sample_period: "January 2009 to December 2021 (test 9 January 2019 to 31 December 2021)"
forecast_object: "implied volatility surface, represented by 16 B-spline coefficients"
horizon: "1, 5, 10, 15 and 20 days"
methods:
  - "nonlinear functional autoregression with a functional neural tangent kernel estimator (fNTK)"
benchmarks:
  - "functional random walk (fRW)"
  - "functional linear, Gaussian and Laplacian kernel regressions"
  - "Carr-Wu, ad-hoc Black-Scholes, DNN-RW and AE-LSTM models"
evaluation_design: "rolling 2500-day window; out-of-sample errors on observed options"
loss_metrics:
  - "RMSE"
  - "out-of-sample R2"
headline_finding: "fNTK has the lowest RMSE at horizons of 5 to 20 days but is not more accurate than the functional random walk one day ahead."
tags:
  - literature
  - literature/forecasting
  - literature/machine-learning
---

# Chen, Grith, and Lai (2026)

**Neural Tangent Kernel in Implied Volatility Forecasting: A Nonlinear Functional Autoregression Approach.** Journal of Business & Economic Statistics 44(1): 24-38.

## Question
- Can a functional autoregression estimated with neural-tangent-kernel networks capture nonlinear dependence between successive surfaces and improve forecasts?

## Data
- IvyDB OptionMetrics S&P 500 calls and puts, 1 January 2009 to 31 December 2021; about 6.4 million observations over 3273 days.

## Method
- Surfaces are projected on 16 orthogonal B-spline basis functions; an NTK-parameterized network maps daily, weekly (5-day mean) and monthly (22-day mean) surface lags to the future surface.

## Evaluation design
- Rolling 2500-day window; test period 9 January 2019 to 31 December 2021; Diebold-Mariano tests.

## Findings
- Overall RMSE, fNTK versus fRW: 3.80 vs 3.71 (h = 1), 4.73 vs 5.75 (h = 5), 5.45 vs 7.69 (h = 10), 5.77 vs 9.30 (h = 15), 5.74 vs 10.61 (h = 20).
- One day ahead, AHBS-VAR, CW-DNN and fLinK are significantly better than fNTK at the 5% level; beyond one day no model is.
- fNTK-based short straddles reach Sharpe ratios of 1.30 to 1.83 at weekly-to-monthly horizons.

## Limits and caveats
- The advantage is confined to multi-day horizons; the authors attribute the one-day result to persistent, linear lag-1 dependence.

## Use in this study
- [[paper#Introduction]]: random-walk benchmarks are hard to beat at short horizons; machine-learning gains are empirical rather than guaranteed.
- [[paper#Literature Review]]: daily, weekly and monthly surface lags carried into a full-surface forecasting model.
- [[paper#Literature Review]]: improvement on a functional random walk at 5 to 20 days, though not one day ahead.
