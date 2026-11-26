---
aliases:
  - "Ulrich, Zimmer, and Merbecks (2023)"
title: "Implied volatility surfaces: a comprehensive analysis using half a billion option prices"
authors:
  - "Maxim Ulrich"
  - "Lukas Zimmer"
  - "Constantin Merbecks"
year: 2023
venue: "Review of Derivatives Research"
doi: "10.1007/s11147-023-09195-5"
status: cited
pdf: "[[lit_review/s11147-023-09195-5.pdf]]"
pdf_version: published
asset_class: "Options on 499 US individual stocks (S&P 500 constituents) and S&P 500 index options"
sample_period: "January 2004-July 2019"
forecast_object: "not a forecasting paper (constructs daily volatility surfaces; accuracy judged by predicting held-out implied volatilities)"
horizon: "not applicable"
methods:
  - "Refined one-dimensional kernel smoother"
benchmarks:
  - "Three-dimensional kernel smoother (OptionMetrics 2022)"
  - "Semi-parametric spline (Figlewski 2008)"
evaluation_design: "Leave-one-out cross-validation within each day's option panel, with and without the outermost strikes; results by moneyness, maturity, volume bucket and industry sector"
loss_metrics:
  - "RMSE"
  - "MAE"
  - "95% quantile of absolute error"
  - "Maximum absolute error"
  - "Error standard deviation"
headline_finding: "The one-dimensional kernel smoother gives the lowest cross-validation errors across moneyness, maturity and volume buckets, and noisier constructions distort option-implied moments and skewness-spanning regressions."
tags:
  - literature
  - literature/surface-construction
---

# Ulrich, Zimmer, and Merbecks (2023)

**Implied volatility surfaces: a comprehensive analysis using half a billion option prices.** Review of Derivatives Research 26: 135-169.

## Question
- Which volatility-surface construction method is most accurate for single-stock options of varying liquidity, and how does the choice affect extracted option-implied information?

## Data
- CBOE daily mid quotes: 373,825,605 prices for options on 499 S&P 500 constituents and 14,267,068 for S&P 500 index options.
- Single-stock options are American; implied volatilities come from the Barone-Adesi and Whaley approximation.

## Method
- One-dimensional kernel smoother: a per-maturity Gaussian kernel over moneyness, linear extrapolation in normalized moneyness, then a second smoothing pass.
- Compared with the OptionMetrics (2022) three-dimensional kernel smoother and the Figlewski spline with an adaptive polynomial order.

## Evaluation design
- Leave-one-out cross-validation within each day's panel, run with and without the outermost strikes.
- Errors are split by moneyness, maturity, trading-volume bucket and GICS sector.

## Findings
- S&P 500 short-term RMSEs (left, center, right) are 0.0090, 0.0029 and 0.0075 for the one-dimensional kernel against 0.5566, 0.1181 and 0.2690 for the three-dimensional kernel.
- For high-volume short-maturity single-stock options, the three-dimensional kernel's RMSEs are 13, 20 and 12 times those of the one-dimensional kernel.
- With the three-dimensional kernel, short-term implied skewness sits near zero and kurtosis is understated; skewness-spanning R-squared and t-statistics fall close to zero.
- The authors say such distortions could "mislead derivative pricing and trading decisions".

## Limits and caveats
- End-of-day US data only.
- The moments and spanning analyses use options with less than 30 days to expiry.
- Dividend-yield and early-exercise measurement error is argued to affect all methods equally.

## Use in this study
- [[paper#Literature Review]]: cited with Ulrich and Walther (2020) for risk-neutral moments such as skewness depending on surface construction.
- [[paper#Literature Review]]: cited (as Ulrich et al. 2023) for surface-construction choices altering extracted option-implied information.
