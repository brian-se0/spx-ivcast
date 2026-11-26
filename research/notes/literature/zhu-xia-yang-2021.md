---
aliases:
  - "Zhu, Xia and Yang (2021)"
title: "Delta Hedging and Volatility-Price Elasticity: A Two-Step Approach"
authors:
  - "Peng Zhu"
  - "Kun Xia"
  - "Xuewei Yang"
year: 2021
venue: "SSRN working paper"
doi: ""
status: uncited
pdf: "[[lit_review/ssrn-3707369.pdf]]"
pdf_version: preprint
asset_class: "S&P 500 index options"
sample_period: "2 January 2004 to 31 August 2015"
forecast_object: "volatility-price elasticity, used to obtain a minimum-variance hedge ratio"
horizon: "daily"
methods:
  - "two-step approach: hedge ratio dependence on volatility-price elasticity, then predicted elasticity"
benchmarks:
  - "related recent minimum-variance hedging methods"
evaluation_design: "not stated"
loss_metrics:
  - "variance of hedging risk"
headline_finding: "Predicting the mean-reverting volatility-price elasticity and plugging it into a stable hedge-ratio model improves hedging performance over related methods."
tags:
  - literature
  - literature/hedging
---

# Zhu, Xia and Yang (2021)

**Delta Hedging and Volatility-Price Elasticity: A Two-Step Approach.** SSRN working paper (April 2021 version).

## Question
- Can short-term properties of the implied volatility-underlying price relation improve minimum-variance delta hedging?

## Data
- S&P 500 daily option data, 2 January 2004 to 31 August 2015.

## Method
- Estimate how the minimum-variance hedge ratio depends on elasticity, then substitute predicted elasticity.

## Evaluation design
- Not stated.

## Findings
- The dependence is stable and elasticity is mean-reverting; hedging improves on related methods.

## Limits and caveats
- Not stated in the parts read.

## Use in this study
Not directly related: forecasts a scalar volatility-price sensitivity for hedging, not the surface.
