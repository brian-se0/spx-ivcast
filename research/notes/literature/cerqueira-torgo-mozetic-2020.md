---
aliases:
  - "Cerqueira, Torgo, and Mozetič (2020)"
title: "Evaluating time series forecasting models: an empirical study on performance estimation methods"
authors:
  - "Vitor Cerqueira"
  - "Luis Torgo"
  - "Igor Mozetič"
year: 2020
venue: "Machine Learning"
doi: "10.1007/s10994-020-05910-7"
status: cited
pdf: "[[lit_review/s10994-020-05910-7.pdf]]"
pdf_version: published
asset_class: "not applicable"
sample_period: "not stated"
forecast_object: "Next value of a univariate time series; the object of study is how well each method estimates a model's out-of-sample loss"
horizon: "1 step"
methods:
  - "Standard K-fold cross-validation (CV)"
  - "Blocked cross-validation (CV-Bl)"
  - "Modified cross-validation (CV-Mod)"
  - "hv-Blocked cross-validation (CV-hvBl)"
  - "Holdout"
  - "Repeated holdout (Rep-Holdout)"
  - "Prequential in blocks (Preq-Bls, Preq-Sld-Bls, Preq-Bls-Gap)"
benchmarks:
  - "Online prequential (Preq-Grow, Preq-Slide)"
evaluation_design: "Each method estimates loss on the first 70% of a series; the true loss is measured on the last 30%; 174 real-world series and three synthetic stationary processes"
loss_metrics:
  - "APAE"
  - "PAE"
  - "RMSE"
headline_finding: "Blocked cross-validation is the best estimator for stationary series, while holdout repeated over multiple test periods is the most accurate for non-stationary series."
tags:
  - literature
  - literature/evaluation
---

# Cerqueira, Torgo, and Mozetič (2020)

**Evaluating time series forecasting models: an empirical study on performance estimation methods.** Machine Learning 109: 1997-2028.

## Question

- Which performance estimation method best approximates the loss a forecasting model will incur on unseen data, for different types of time series?

## Data

- 174 real-world univariate series from several domains, each with at least 500 observations and truncated to 4000; a wavelet spectrum test classifies 97 as stationary and 77 as non-stationary.
- Three synthetic stationary processes, 1000 Monte Carlo series of 200 values each.

## Method

- Eleven estimation methods: cross-validation variants, out-of-sample holdout variants, and prequential variants, with 10 folds or repetitions.
- Learners: rule-based regression, random forest, and a ridge-penalised generalised linear model on lagged values.

## Evaluation design

- Each method's estimate on the first 70% of a series is compared with the refitted model's loss on the remaining 30%.
- Methods are ranked by absolute predictive accuracy error and compared with a Bayes signed-rank test.

## Findings

- Stationary series: CV-Bl has the best average rank; CV-Bl and CV-hvBl are significantly better than Rep-Holdout.
- Non-stationary series: Rep-Holdout ranks best, followed by the blocked cross-validation variants; standard CV ranks worst.
- Rep-Holdout beats single Holdout in both groups; Preq-Bls is the best prequential variant.
- Standard CV, CV-Mod and the online prequential methods tend to under-estimate error.

## Limits and caveats

- Univariate numeric series and one-step forecasts only; the sample-size analysis stops at 1000 observations.
- Results are phrased as what the experiments suggest; domain-specific series such as finance are left to future work.

## Use in this study

- [[paper#Literature Review]]: evidence that time-series evaluation should respect serial dependence and non-stationarity, with repeated out-of-sample holdouts most accurate and standard cross-validation least accurate for non-stationary series, and blocked cross-validation suited to stationary series.
