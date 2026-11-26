---
aliases:
  - "Yang, Chen, Shu and Hospedales (2025)"
title: "HyperIV: Real-time Implied Volatility Smoothing"
authors:
  - "Yongxin Yang"
  - "Wenqi Chen"
  - "Chao Shu"
  - "Timothy Hospedales"
year: 2025
venue: "Proceedings of the 42nd International Conference on Machine Learning (PMLR 267)"
doi: ""
status: uncited
pdf: "[[lit_review/YangEtalICML2025HyperIVReal-time.pdf]]"
pdf_alt: "[[lit_review/ssrn-5078198.pdf]]"
pdf_version: accepted-manuscript
asset_class: "index options (S&P 500, NASDAQ 100, Russell 2000, VIX, MSCI World, MSCI Emerging Markets)"
sample_period: "training before 2023-08-01 (one-minute) or 2023-01-01 (daily); later data for testing"
forecast_object: "construction of complete arbitrage-free surfaces from 9 observations"
horizon: "not applicable"
methods:
  - "hypernetwork generating a compact neural network"
benchmarks:
  - "SSVI"
  - "VAE"
  - "GNO"
evaluation_design: "chronological train-test split; one model per asset-interval; cross-asset generalization tested"
loss_metrics:
  - "not stated"
headline_finding: "HyperIV builds a static-arbitrage-free surface in 2 milliseconds from 9 observations and is more accurate than existing methods."
tags:
  - literature
  - literature/surface-construction
  - literature/machine-learning
---

# Yang, Chen, Shu and Hospedales (2025)

**HyperIV: Real-time Implied Volatility Smoothing.** ICML 2025.

## Question
- How can full surfaces be built in real time from very sparse high-frequency quotes?

## Data
- 8 index options, one-minute and end-of-day; over 150,000 surfaces.

## Method
- Hypernetwork outputs parameters of a small network; arbitrage-freeness is guaranteed.

## Evaluation design
- Train on earlier data and test on later intervals.

## Findings
- Superior accuracy versus SSVI, VAE and GNO baselines.

## Limits and caveats
- Smoothing of the current surface, not forecasting.

## Use in this study
Relates to surface construction from sparse quotes; it does not forecast future surfaces.
