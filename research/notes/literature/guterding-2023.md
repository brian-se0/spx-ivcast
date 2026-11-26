---
aliases:
  - "Guterding (2023)"
title: "Sparse Modeling Approach to the Arbitrage-Free Interpolation of Plain-Vanilla Option Prices and Implied Volatilities"
authors:
  - "Daniel Guterding"
year: 2023
venue: "Risks"
doi: "10.3390/risks11050083"
status: cited
pdf: "[[lit_review/risks-11-00083.pdf]]"
pdf_version: published
asset_class: "S&P 500 (SPX) one-month index options; synthetic option prices"
sample_period: "single day: 5 February 2018 (SPX); synthetic data otherwise"
forecast_object: "not a forecasting paper; implies a terminal density and arbitrage-free smile at one maturity"
horizon: "not applicable"
methods:
  - "Truncated singular value decomposition of the price-density kernel matrix"
  - "Constrained, L1-regularized least-squares optimization (CVXPY, ECOS)"
benchmarks: []
evaluation_design: "not applicable (recovery of known densities; in-sample fit to one market smile)"
loss_metrics:
  - "Squared error in prices"
  - "Bhattacharyya distance between implied and exact density"
headline_finding: "A truncated-SVD, L1-regularized, constrained optimization recovers a non-negative terminal density from option prices at a single maturity, giving arbitrage-free interpolation and extrapolation without pre-processing the inputs."
tags:
  - literature
  - literature/surface-construction
  - literature/no-arbitrage
---

# Guterding (2023)

**Sparse Modeling Approach to the Arbitrage-Free Interpolation of Plain-Vanilla Option Prices and Implied Volatilities.** Risks 11: 83.

## Question
- Can a continuous, arbitrage-free representation of option prices and implied volatilities be built from discretely quoted strikes without specifying a stochastic process or functional form?

## Data
- Synthetic prices of 200 call and put options from a normal density, a log-normal density, a three-component normal mixture, and a mixture with a negative weight whose prices contain arbitrage.
- SPX one-month options on 5 February 2018, 75 strikes between 1900 and 2900, from Le Floc'h and Osterlee (2019a).

## Method
- Writes prices as a kernel matrix applied to a density discretized on 1000 points; the kernel is ill-conditioned.
- Keeps the Q largest singular values and minimizes squared price error plus an L1 penalty λ on the transformed density, subject to a non-negative density integrating to one.
- Chooses the largest λ that keeps the price error near its minimum.

## Evaluation design
- Recovery of known densities over a range of λ; for SPX, reproduction of input volatilities.

## Findings
- Normal and log-normal densities are recovered closely near λ ≈ 10^-7.5, the multimodal density near 10^-8.5.
- Inputs containing arbitrage yield a non-negative density and a de-arbitraged smile very similar to the original.
- The SPX smile, including a kink near strike 2800, is reproduced with Q = 70.

## Limits and caveats
- Handles many strikes but a single time to maturity; multiple maturities are left to future work.
- A regularization parameter must be chosen; bid-ask spreads are not used.
- Extrapolation beyond quoted strikes is described as speculative.

## Use in this study
- [[paper#Literature Review]]: arbitrage-free interpolation across finitely many strikes at one maturity.
- [[paper#Literature Review]]: constrained interpolation that treats smoothing or completion as its own problem.
- [[paper#Literature Review]]: single-maturity case showing dense recovery is a modeling task.
