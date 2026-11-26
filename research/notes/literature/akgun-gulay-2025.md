---
aliases:
  - "Akgun and Gulay (2025)"
title: "Dynamics in Realized Volatility Forecasting: Evaluating GARCH Models and Deep Learning Algorithms Across Parameter Variations"
authors:
  - "Omer Burak Akgun"
  - "Emrah Gulay"
year: 2025
venue: "Computational Economics"
doi: "10.1007/s10614-024-10694-2"
status: uncited
pdf: "[[lit_review/s10614-024-10694-2.pdf]]"
pdf_version: published
asset_class: "top three cryptocurrencies by trading volume"
sample_period: "not stated"
forecast_object: "realized volatility (5-minute realized variance and median realized variance)"
horizon: "not stated"
methods:
  - "eleven GARCH-type models in six distributions"
  - "deep learning algorithms"
benchmarks:
  - "GARCH-type models"
evaluation_design: "expanding versus rolling windows and varying training/test ratios"
loss_metrics:
  - "several error measures (not itemised in the parts read)"
headline_finding: "Deep learning models outperform GARCH-type models in volatility forecasts, and rolling windows and larger training/test ratios improve accuracy."
tags:
  - literature
  - literature/volatility-forecasting
  - literature/machine-learning
---

# Akgun and Gulay (2025)

**Dynamics in Realized Volatility Forecasting: Evaluating GARCH Models and Deep Learning Algorithms Across Parameter Variations.** Comput. Econ. 65: 3971-4013.

## Question
- How do realized-variance measure, training size, window type and error measure affect volatility forecast comparisons between GARCH models and deep learning?

## Data
- Realized volatility of the three most traded cryptocurrencies; period not stated in the parts read.

## Method
- Eleven GARCH-type models and deep learning algorithms forecast two realized variance versions.

## Evaluation design
- Expanding versus rolling windows; varied training/test ratio; several error measures.

## Findings
- 5-minute realized variance works best for GARCH models, median realized variance for deep learning; deep learning wins overall.

## Limits and caveats
- Cryptocurrency return volatility only.

## Use in this study
Not directly related.
