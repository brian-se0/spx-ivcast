---
aliases:
  - "Ulrich and Walther (2020)"
title: "Option-implied information: What's the vol surface got to do with it?"
authors:
  - "Maxim Ulrich"
  - "Simon Walther"
year: 2020
venue: "Review of Derivatives Research"
doi: "10.1007/s11147-020-09166-0"
status: cited
pdf: "[[lit_review/s11147-020-09166-0.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options (CBOE) and Euro Stoxx 50 index options (Eurex)"
sample_period: "S&P 500: January 2004-July 2017 end-of-day, January 2004-October 2017 intraday; Euro Stoxx 50: January 2002-September 2017 end-of-day, January 2003-September 2017 intraday"
forecast_object: "not a forecasting paper (constructs volatility surfaces; accuracy judged by predicting held-out implied volatilities)"
horizon: "not applicable"
methods:
  - "One-dimensional kernel regression with linear tail extrapolation and no-arbitrage post-processing"
benchmarks:
  - "Three-dimensional kernel regression (OptionMetrics 2016)"
  - "Spline interpolation (Figlewski 2008)"
  - "Gram-Charlier expansion (Beber and Brandt 2006)"
evaluation_design: "Leave-one-out cross-validation on end-of-day panels; intraday, each trade predicted from the preceding 3, 4, 5 or 10 trades"
loss_metrics:
  - "RMSE"
  - "MAE"
  - "Smoothness (squared second derivative along moneyness)"
headline_finding: "Option-implied variance, skewness and variance-risk-premium estimates depend materially on how the volatility surface is constructed, and a one-dimensional kernel regression is generally the most accurate construction."
tags:
  - literature
  - literature/surface-construction
---

# Ulrich and Walther (2020)

**Option-implied information: What's the vol surface got to do with it?** Review of Derivatives Research 23: 323-355.

## Question
- How much do option-implied variance, skewness and the variance risk premium depend on the method used to build the volatility surface, and which method represents option prices most accurately?

## Data
- End-of-day and intraday S&P 500 options (CBOE Livevol) and Euro Stoxx 50 options; 9,246,926 end-of-day S&P 500 price observations.
- Out-of-the-money options only, after no-arbitrage filters.

## Method
- Proposes a kernel regression over moneyness alone, run separately for each maturity, with linear tail extrapolation and a no-arbitrage post-processing step.
- Compares it with the OptionMetrics three-dimensional kernel regression, the Figlewski spline and a Gram-Charlier expansion.

## Evaluation design
- Leave-one-out cross-validation on each end-of-day panel; intraday, each trade is predicted from the preceding 3, 4, 5 or 10 trades at the same maturity.
- Model-free moments and a one-month variance risk premium are recomputed under each surface with everything else held fixed.

## Findings
- Average medium-term S&P 500 model-free implied volatility is 21.0% under the three-dimensional kernel and 23.5% under the spline.
- Average annualized one-month S&P 500 variance risk premium ranges from 1.5% to 2.4% across surfaces; the spline figure is 60% above the three-dimensional-kernel figure.
- Skewness from the three-dimensional kernel is roughly half the size of the one-dimensional-kernel and spline estimates, and sub-period changes can differ in sign.
- The one-dimensional kernel has the lowest end-of-day S&P 500 cross-validation RMSE (0.0092) and MAE (0.0019).

## Limits and caveats
- Two index-option markets only.
- For end-of-day Euro Stoxx 50 data the spline has the lower MAE, and intraday the spline attains the lowest MAE once more trades are used.
- Accuracy is presented as one of several practical criteria for choosing a construction method.

## Use in this study
- [[paper#Introduction]]: cited among the sources for why the full surface, not a single volatility summary, matters for extracting option-implied state variables.
- [[paper#Literature Review]]: cited for risk-neutral variance and variance-risk-premium estimates changing with surface construction.
- [[paper#Literature Review]]: cited for surface-construction choices altering extracted option-implied information.
