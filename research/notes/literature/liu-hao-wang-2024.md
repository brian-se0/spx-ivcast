---
aliases:
  - "Liu, Hao and Wang (2024)"
title: "Solving the Forecast Combination Puzzle Using Double Shrinkages"
authors:
  - "Li Liu"
  - "Xianfeng Hao"
  - "Yudong Wang"
year: 2024
venue: "Oxford Bulletin of Economics and Statistics"
doi: "10.1111/obes.12590"
status: uncited
pdf: "[[lit_review/Solving the Forecast Combination Puzzle Using Double Shrinkages_.pdf]]"
pdf_version: published
asset_class: "S&P 500 index excess returns"
sample_period: "January 1947 to December 2017"
forecast_object: "monthly excess returns of the S&P 500 (also macroeconomic indicators)"
horizon: "not stated"
methods:
  - "double shrinkage combination (weighted least squares plus LASSO, ridge or elastic net)"
benchmarks:
  - "historical average"
  - "equal-weighted combination"
evaluation_design: "out-of-sample"
loss_metrics:
  - "out-of-sample R2"
  - "MSPE"
  - "certainty equivalent return"
headline_finding: "Shrinking combination weights toward equal weights and toward zero beats the equal-weighted combination."
tags:
  - literature
  - literature/forecast-combination
---

# Liu, Hao and Wang (2024)

**Solving the Forecast Combination Puzzle Using Double Shrinkages.** Oxford Bulletin of Economics and Statistics 86(3).

## Question
- Can regularized weights beat equal-weight forecast combination?

## Data
- Twelve economic predictors for S&P 500 excess returns, 1947-2017.

## Method
- WLS shrinkage toward equal weights plus LASSO/ridge/elastic-net shrinkage toward zero.

## Evaluation design
- Out-of-sample against the historical average and equal-weight combination.

## Findings
- Out-of-sample R2 above 0.95% and MSPE about 0.45% lower than equal weights.

## Limits and caveats
- Return forecasting, not volatility surfaces.

## Use in this study
Relates only as background on combining forecasts and on ridge and elastic-net regularization.
