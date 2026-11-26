---
aliases:
  - "Vrontos, Galakis, and Vrontos (2021)"
title: "Implied volatility directional forecasting: a machine learning approach"
authors:
  - "Spyridon D. Vrontos"
  - "John Galakis"
  - "Ioannis D. Vrontos"
year: 2021
venue: "Quantitative Finance"
doi: "10.1080/14697688.2021.1905869"
status: cited
pdf: "[[lit_review/Implied volatility directional forecasting  a machine learning approach.pdf]]"
pdf_version: published
asset_class: "CBOE VIX index"
sample_period: "January 1990 to December 2019 (out-of-sample January 2004 to December 2019)"
forecast_object: "direction (rise or fall) of the VIX index, as a binary variable"
horizon: "1 month"
methods:
  - "Ridge, LASSO and Elastic Net Logit"
  - "linear and regularized discriminant analysis"
  - "Naive Bayes and Bayesian GLM"
  - "bagging, random forest, adaptive and gradient boosting"
  - "k-nearest neighbor and recursive partitioning"
benchmarks:
  - "univariate Logit"
  - "stepwise multiple Logit (AIC, BIC, Deviance)"
  - "forecast combinations"
evaluation_design: "recursive expanding window; 192 one-month-ahead out-of-sample forecasts"
loss_metrics:
  - "AUC"
  - "misclassification error"
  - "accuracy"
  - "Pesaran-Timmermann statistic"
headline_finding: "Machine-learning classifiers, led by Naive Bayes and adaptive boosting, forecast the monthly direction of the VIX more accurately than univariate and stepwise Logit models."
tags:
  - literature
  - literature/volatility-forecasting
  - literature/machine-learning
---

# Vrontos, Galakis, and Vrontos (2021)

**Implied volatility directional forecasting: a machine learning approach.** Quantitative Finance 21(10): 1687-1706.

## Question
- Can the direction of the VIX index be forecast, and do machine-learning techniques do it better than standard econometric models?

## Data
- Monthly data, January 1990 to December 2019; 31 macroeconomic and financial-market predictors with up to three lags, plus lags of the directional indicator.

## Method
- Binary Logit models, alone and with stepwise selection, are the standard econometric models.
- Elastic Net preselects predictors at each step; penalized Logit, discriminant, Bayesian, tree-ensemble, boosting, k-nn and partitioning classifiers are then fitted.

## Evaluation design
- In-sample February 1990 to December 2003; out-of-sample January 2004 to December 2019, with selection and estimation repeated at each step.

## Findings
- Best univariate Logit (three VIX lags): accuracy 59.9%; stepwise BIC Logit: 61.5%.
- With Elastic Net preselection at alpha 0.50, Naive Bayes and adaptive boosting reach accuracy 65.6% and Pesaran-Timmermann statistics of 4.49 and 4.248.
- Forecast combinations mostly fail to beat the top machine-learning techniques.
- Accuracy is not consistent across the machine-learning models.

## Limits and caveats
- The target is the sign of the monthly change in a single index, not a level or a surface.

## Use in this study
- [[paper#Literature Review]]: implied-volatility forecasting work outside the full-surface setting that compares machine-learning models with linear, penalized and parametric alternatives.
