---
aliases:
  - "Chataigner, Crepey and Dixon (2020)"
title: "Deep Local Volatility"
authors:
  - "Marc Chataigner"
  - "Stéphane Crépey"
  - "Matthew Dixon"
year: 2020
venue: "Risks"
doi: "10.3390/risks8030082"
status: uncited
pdf: "[[lit_review/risks-08-00082.pdf]]"
pdf_version: published
asset_class: "DAX vanilla options"
sample_period: "not stated"
forecast_object: "not a forecasting paper (interpolation of option prices and local volatility surface)"
horizon: "not applicable"
methods:
  - "feed-forward neural network with no-arbitrage constraints"
  - "Dupire-formula bounds on local volatility"
benchmarks:
  - "hard-constraint and soft-constraint network variants"
evaluation_design: "training grid versus out-of-sample test grid of contracts"
loss_metrics:
  - "pricing RMSE"
headline_finding: "A neural network can interpolate vanilla option prices while jointly yielding a local volatility surface and enforcing or favouring no-arbitrage."
tags:
  - literature
  - literature/surface-construction
  - literature/no-arbitrage
---

# Chataigner, Crepey and Dixon (2020)

**Deep Local Volatility.** Risks 8(3): 82.

## Question
- Can deep learning interpolate option prices under no-arbitrage conditions and give the full local volatility surface?

## Data
- Real DAX vanilla option datasets (figures show 8 August 2001).

## Method
- Loss or architecture modified to enforce (hard) or favour (soft) no-arbitrage; Dupire formula bounds local volatility during fitting.

## Evaluation design
- Evaluated on training and out-of-sample test sets; pricing RMSE reported.

## Findings
- The experimental design parameters needed for adequate performance are specified.

## Limits and caveats
- Single-date interpolation; no forecasting.

## Use in this study
Relevant to surface construction and no-arbitrage constraints on neural-network surfaces.
