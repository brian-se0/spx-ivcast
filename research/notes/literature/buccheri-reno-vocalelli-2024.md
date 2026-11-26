---
aliases:
  - "Buccheri, Reno and Vocalelli (2024)"
title: "Taking advantage of biased proxies for forecast evaluation"
authors:
  - "Giuseppe Buccheri"
  - "Roberto Renò"
  - "Giorgio Vocalelli"
year: 2024
venue: "SSRN working paper"
doi: ""
status: uncited
pdf: "[[lit_review/ssrn-4628161.pdf]]"
pdf_version: preprint
asset_class: "GDP growth and financial market volatility (details not stated)"
sample_period: "not stated"
forecast_object: "ranking of competing forecasts of GDP growth and volatility using proxies for the latent target"
horizon: "not stated"
methods:
  - "optimal combination of possibly biased proxies"
  - "Diebold-Mariano equal predictive accuracy test with robust loss"
benchmarks:
  - "unbiased proxy (5-minute realized volatility in the volatility application)"
evaluation_design: "forecast comparison with proxy-based loss"
loss_metrics:
  - "robust loss functions in the sense of Patton (2011)"
headline_finding: "Combining possibly biased proxies maximises the probability of recovering the ranking implied by the true latent variable while preserving loss robustness and Diebold-Mariano testing."
tags:
  - literature
  - literature/evaluation
  - literature/volatility-forecasting
---

# Buccheri, Reno and Vocalelli (2024)

**Taking advantage of biased proxies for forecast evaluation.** SSRN working paper (July 2024 version).

## Question
- Can biased proxies still support valid forecast ranking when the true target is latent?

## Data
- Empirical applications to GDP growth and volatility; a HAR comparison (levels versus logs) uses 5-minute and 10-second realized volatility.

## Method
- Optimal shrinkage-type combination of proxies; "proxy reliability" is the probability of inferring the true-target ranking.

## Evaluation design
- Equal predictive accuracy tests as in Diebold and Mariano (1995).

## Findings
- The method is useful in the empirical applications shown.

## Limits and caveats
- Sample details not read.

## Use in this study
Relevant to forecast evaluation with Diebold-Mariano tests when the target is measured with proxy error.
