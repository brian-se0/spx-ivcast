---
aliases:
  - "Bergeron, Fung, Hull, Poulos and Veneris (2022)"
title: "Variational Autoencoders: A Hands-Off Approach to Volatility"
authors:
  - "Maxime Bergeron"
  - "Nicholas Fung"
  - "John Hull"
  - "Zissis Poulos"
  - "Andreas Veneris"
year: 2022
venue: "The Journal of Financial Data Science (Spring 2022)"
doi: ""
status: uncited
pdf: "[[lit_review/EBSCO-FullText-02_08_2026.pdf]]"
pdf_version: published
asset_class: "FX options"
sample_period: "validation set March 2020 to December 2020; full period not stated"
forecast_object: "completion and synthetic generation of volatility surfaces"
horizon: "not applicable"
methods:
  - "variational autoencoder with latent-space fitting to partial surfaces"
benchmarks: []
evaluation_design: "chronological train/validation split (validation about 15% of data)"
loss_metrics: []
headline_finding: "VAEs generate realistic synthetic surfaces and complete surfaces from few points; pooling currency pairs improves results."
tags:
  - literature
  - literature/surface-construction
---

# Bergeron, Fung, Hull, Poulos and Veneris (2022)

**Variational Autoencoders: A Hands-Off Approach to Volatility.** The Journal of Financial Data Science, Spring 2022.

## Question
- Can VAEs model volatility surfaces and fill in missing points without assumptions on the underlying process?

## Data
- Exchange Data International FX data on a 40-point grid (eight maturities, five deltas).

## Method
- Train a VAE, then search the latent space for the surface that best fits available quotes.

## Evaluation design
- Chronological split to prevent leakage.

## Findings
- Pooling data from multiple currency pairs improves results.

## Limits and caveats
- FX options; static completion rather than forecasting.

## Use in this study
Relates to surface completion and generation, not to forecasting the SPX surface one session ahead.
