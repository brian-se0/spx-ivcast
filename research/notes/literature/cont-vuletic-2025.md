---
aliases:
  - "Cont and Vuletic (2025)"
title: "Data-driven hedging with generative models"
authors:
  - "Rama Cont"
  - "Milena Vuletić"
year: 2025
venue: "Annals of Operations Research"
doi: "10.1007/s10479-025-06867-3"
status: uncited
pdf: "[[lit_review/s10479-025-06867-3.pdf]]"
pdf_version: published
asset_class: "SPX options"
sample_period: "3 January 2000 to 28 February 2023 (training to 16 June 2018, out-of-sample afterwards)"
forecast_object: "simulated scenarios of implied volatility surface dynamics used to compute hedge ratios"
horizon: "not stated"
methods:
  - "VolGAN conditional generative model for implied volatility surfaces"
  - "scenario-based risk-minimising hedge ratios with transaction costs"
benchmarks:
  - "delta hedging"
  - "delta-vega hedging"
evaluation_design: "train 2000 to June 2018; out-of-sample hedging experiment over non-overlapping periods without retraining"
loss_metrics: []
headline_finding: "The generative-model hedge matches and improves on delta and delta-vega hedging out of sample, without retraining for more than 4 years after the training period."
tags:
  - literature
  - literature/hedging
  - literature/surface-dynamics
---

# Cont and Vuletic (2025)

**Data-driven hedging with generative models.** Ann. Oper. Res.

## Question
- Can a conditional generative model trained on market data replace model-based sensitivities for hedging option portfolios?

## Data
- SPX options from OptionMetrics, Jan 2000 to 28 Feb 2023; smooth IV and bid-ask spread surfaces from vega-weighted Nadaraya-Watson kernel smoothing.

## Method
- VolGAN simulates surface scenarios given current conditions; hedge ratios minimise risk across scenarios and include transaction costs.

## Evaluation design
- Training through 16 June 2018, out-of-sample testing afterwards, against delta and delta-vega hedging.

## Findings
- Out-of-sample performance matches or improves on the benchmarks without retraining for over 4 years.

## Limits and caveats
- The surface model is used for hedging, not evaluated as a surface forecast in the parts read.

## Use in this study
Uses a generative SPX implied-volatility-surface model (VolGAN) with the same kernel-smoothed surface construction, though for hedging rather than next-session forecast comparison.
