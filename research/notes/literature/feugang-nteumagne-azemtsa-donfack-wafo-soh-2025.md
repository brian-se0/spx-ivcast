---
aliases:
  - "Feugang Nteumagné, Azemtsa Donfack and Wafo Soh (2025)"
title: "Variational Autoencoders for Completing the Volatility Surfaces"
authors:
  - "Bienvenue Feugang Nteumagné"
  - "Hermann Azemtsa Donfack"
  - "Celestin Wafo Soh"
year: 2025
venue: "Journal of Risk and Financial Management"
doi: "10.3390/jrfm18050239"
status: uncited
pdf: "[[lit_review/jrfm-18-00239.pdf]]"
pdf_version: published
asset_class: "synthetic volatility surfaces"
sample_period: "not applicable (synthetic data)"
forecast_object: "reconstruction of sparse volatility surfaces"
horizon: "not applicable"
methods:
  - "variational autoencoder with latent space optimization"
benchmarks:
  - "thin-plate spline interpolation"
  - "SABR"
  - "SVI"
  - "deterministic autoencoder"
evaluation_design: "reconstruction from sparse subsets of synthetic surfaces"
loss_metrics:
  - "reconstruction error"
headline_finding: "The VAE reconstructs arbitrage-free surfaces from 5% of points, with errors 7-12 times lower than competitors under high sparsity."
tags:
  - literature
  - literature/surface-construction
---

# Feugang Nteumagné, Azemtsa Donfack and Wafo Soh (2025)

**Variational Autoencoders for Completing the Volatility Surfaces.** Journal of Risk and Financial Management 18(5): 239.

## Question
- Can VAEs complete volatility surfaces under extreme data sparsity?

## Data
- Over 13,500 synthetic, arbitrage-free surfaces used for training.

## Method
- VAE with latent space optimization.

## Evaluation design
- Comparison with splines, SABR, SVI and deterministic autoencoders at varying sparsity.

## Findings
- No-arbitrage conditions are checked through density and total variance strip tests.

## Limits and caveats
- Synthetic data only.

## Use in this study
Relates to surface completion with machine learning, not to forecasting.
