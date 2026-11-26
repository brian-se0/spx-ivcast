---
aliases:
  - "Ning, Jaimungal, Zhang and Bergeron (2022)"
title: "Arbitrage-Free Implied Volatility Surface Generation with Variational Autoencoders"
authors:
  - "Brian (Xin) Ning"
  - "Sebastian Jaimungal"
  - "Xiaorong Zhang"
  - "Maxime Bergeron"
year: 2022
venue: "arXiv:2108.04941v3 [q-fin.MF]"
doi: ""
status: uncited
pdf: "[[lit_review/2108.04941v3.pdf]]"
pdf_version: preprint
asset_class: "FX options (AUD-USD, EUR-USD, CAD-USD)"
sample_period: "September 18, 2012 to December 30, 2019 (1,900 days)"
forecast_object: "generation of arbitrage-free implied volatility surfaces consistent with history"
horizon: "not applicable"
methods:
  - "variational autoencoder over SDE model parameters"
  - "regime switching and Levy additive models"
benchmarks: []
evaluation_design: "chronological split: train Sep 18, 2012 to May 9, 2016; test May 10, 2016 to Dec 30, 2019"
loss_metrics:
  - "RMSE"
headline_finding: "A VAE on SDE-model parameters generates arbitrage-free surfaces and a conditional version improves out-of-sample generative performance."
tags:
  - literature
  - literature/surface-construction
  - literature/no-arbitrage
---

# Ning, Jaimungal, Zhang and Bergeron (2022)

**Arbitrage-Free Implied Volatility Surface Generation with Variational Autoencoders.** arXiv:2108.04941v3.

## Question
- How can historically consistent, arbitrage-free IV surfaces be generated from sparse data?

## Data
- Exchange Data International FX option data: five strikes at each of eight maturities (1M to 5Y).

## Method
- Project surfaces onto SDE parameters, train a VAE, decode samples back to surfaces.

## Evaluation design
- Equal chronological train/test split; a 2019 test window is also used.

## Findings
- Conditional features improve out-of-sample generation.

## Limits and caveats
- FX options with sparse quotes; generation, not point forecasting.

## Use in this study
Relates to generative modelling of surfaces, not to next-session point forecasts of the SPX surface.
