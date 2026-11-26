---
aliases:
  - "Chen, Li, and Yu (2024)"
title: "Modeling Implied Volatility Surface Using B-Splines with Time-Dependent Coefficients Predicted by Tree-Based Machine Learning Methods"
authors:
  - "Zihao Chen"
  - "Yuyang Li"
  - "Cindy Long Yu"
year: 2024
venue: "Mathematics"
doi: "10.3390/math12071100"
status: cited
pdf: "[[lit_review/mathematics-12-01100-v3.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options"
sample_period: "January 2015 - April 2022"
forecast_object: "log implied volatility of individual options, through predicted B-spline coefficients of the surface"
horizon: "1 day"
methods:
  - "Penalized bivariate tensor-product B-splines (additive B-splines in the empirical study)"
  - "Gradient boosted regression trees on five lags of the spline coefficients"
  - "Bayesian optimization with a Gaussian process for hyperparameter tuning"
benchmarks:
  - "Parametric log implied volatility regression of Goncalves and Guidolin (2006)"
  - "Dynamic parametric benchmark (same regression with tree-predicted coefficients)"
  - "Nonparametric gradient boosted trees on moneyness and time to maturity"
evaluation_design: "rolling window with 60-day training, 20-day validation and 1-day test, shifted one day at a time from March 2015 to April 2022"
loss_metrics:
  - "RMSE"
  - "relative RMSE"
headline_finding: "The dynamic additive B-spline model with tree-predicted coefficients has the lowest out-of-sample RMSE (0.2016), ahead of the nonparametric (0.2455), parametric (0.2962) and dynamic parametric (3.8606) benchmarks."
tags:
  - literature
  - literature/forecasting
  - literature/machine-learning
---

# Chen, Li, and Yu (2024)

**Modeling Implied Volatility Surface Using B-Splines with Time-Dependent Coefficients Predicted by Tree-Based Machine Learning Methods.** Mathematics 12, 1100.

## Question
- Does forecasting the coefficients of a fixed B-spline basis with tree-based learners predict the implied volatility surface better than parametric regressions and direct machine-learning fits?

## Data
- Daily S&P 500 option prices from OptionMetrics, January 2015 to April 2022.
- Filters include time to maturity between 6 and 365 days and strike within 10% of spot.
- Calls and puts are modelled separately; reported results are for calls.

## Method
- Step 1: a penalized B-spline surface is fitted to log implied volatility; its coefficient vector represents the day's surface. The empirical study uses additive cubic B-splines in moneyness and maturity, because the tensor-product form produces extreme coefficients.
- Step 2: gradient boosted regression trees predict the coefficients from their five lags; hyperparameters are tuned by Bayesian optimization.

## Evaluation design
- Rolling scheme: 60 training days, 20 validation days, 1 test day, starting March 2015.
- A simulation checks the tensor-product spline against a known parametric surface.

## Findings
- Out-of-sample RMSE: dynamic additive B-splines 0.2016, nonparametric 0.2455, parametric 0.2962, dynamic parametric 3.8606.
- The proposed model has the lowest RMSE for in-the-money and out-of-the-money options and for overvalued and undervalued options.
- In sample, additive B-splines give RMSE 0.0532 against 0.0702 for the parametric model.
- Simulation relative RMSE on a grid ranges from 0.83% to 5.93%.

## Limits and caveats
- Statistical tests of forecast differences: not stated.
- No-arbitrage conditions on the fitted surface: not stated.
- In the simulation the spline fits poorly near the boundary.

## Use in this study
- [[paper#Introduction]]: one of the recent machine-learning approaches (coefficient model) whose gains are empirical.
- [[paper#Literature Review]]: example of tree-based prediction of B-spline coefficients outperforming parametric and nonparametric benchmarks.
