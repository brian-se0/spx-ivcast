---
aliases:
  - "Aït-Sahalia, Li and Li (2021)"
title: "Implied Stochastic Volatility Models"
authors:
  - "Yacine Aït-Sahalia"
  - "Chenxu Li"
  - "Chen Xu Li"
year: 2021
venue: "The Review of Financial Studies"
doi: "10.1093/rfs/hhaa041"
status: uncited
pdf: "[[lit_review/hhaa041.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options"
sample_period: "January 3, 2007 to December 29, 2017"
forecast_object: "implied volatility surface fitted by stochastic volatility models"
horizon: "not stated"
methods:
  - "implied stochastic volatility model (nonparametric, or parametric via GMM)"
benchmarks: []
evaluation_design: "in-sample and out-of-sample implied-volatility pricing errors"
loss_metrics:
  - "IVRMSE"
headline_finding: "The method is stable and performs well out of sample on S&P 500 options."
tags:
  - literature
  - literature/surface-construction
---

# Aït-Sahalia, Li and Li (2021)

**Implied Stochastic Volatility Models.** The Review of Financial Studies 34(1): 394-450.

## Question
- Can shape characteristics of the IV surface be linked to the coefficient functions of a stochastic volatility model?

## Data
- OptionMetrics S&P 500 options, 1,411,612 raw observations, 2007-2017.

## Method
- Estimate shape characteristics, then back out the model, nonparametrically or by GMM.

## Evaluation design
- In- and out-of-sample IVRMSE.

## Findings
- Stable estimation and good out-of-sample performance.

## Limits and caveats
- Out-of-sample design details are not stated in the pages read.

## Use in this study
Relates to model-based fitting of the SPX surface, a structural alternative to the statistical forecasting models compared here.
