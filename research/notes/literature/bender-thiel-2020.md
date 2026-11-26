---
aliases:
  - "Bender and Thiel (2020)"
title: "Arbitrage-free interpolation of call option prices"
authors:
  - "Christian Bender"
  - "Matthias Thiel"
year: 2020
venue: "Statistics & Risk Modeling (printed as Stat. Risk Model.)"
doi: "10.1515/strm-2018-0026"
status: cited
pdf: "[[lit_review/pdf.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options; simulated Merton-model call prices"
sample_period: "October 1995 (S&P 500 implied volatility table); simulated data otherwise"
forecast_object: "not a forecasting paper; interpolates call prices and implied volatilities"
horizon: "not applicable"
methods:
  - "Reference-model-based C1 and C2 interpolation of call prices in strike (generalized Kahalé method)"
  - "Linear interpolation in implied total variance across maturities"
  - "Quadratic-program pre- and post-processing against strike and calendar arbitrage"
benchmarks:
  - "Fengler (2009) cubic smoothing spline"
  - "Kahalé (2004) interpolation (Gaussian reference case)"
evaluation_design: "not applicable (numerical test cases)"
loss_metrics:
  - "Maximal relative error of call prices"
headline_finding: "For a single maturity, distorting a chosen reference model's call price function gives a smooth interpolant of quoted prices that is free of static arbitrage by construction, with Kahalé's method as the Gaussian special case."
tags:
  - literature
  - literature/surface-construction
  - literature/no-arbitrage
---

# Bender and Thiel (2020)

**Arbitrage-free interpolation of call option prices.** Stat. Risk Model. 37(1-2): 55-78.

## Question
- How can call prices quoted at finitely many strikes and maturities be inter- and extrapolated smoothly and without static arbitrage, using a reference model of one's choice?

## Data
- Lab data: 12 call prices at maturity 0.2 years from a Merton jump-diffusion model.
- S&P 500 implied volatilities for October 1995, 10 strikes by 10 maturities (0.175 to 5 years), from Andersen and Brotherton-Ratcliffe.

## Method
- For one maturity, builds the pricing distribution piecewise between strikes from linear transformations of a reference log-price distribution, matching quoted prices and slopes; an iterative algorithm picks slopes for a continuous second derivative (convergence is conjectured).
- Inputs must be free of strike arbitrage; otherwise a least-squares step adjusts them.
- Across maturities, curves are interpolated linearly in implied total variance, followed by grid-based post-processing against remaining calendar or strike arbitrage.

## Evaluation design
- Illustrative cases, including refitting after removing half of the strikes.

## Findings
- The interpolant reproduces the reference model's prices when the data are compatible with it (Theorem 4.3).
- A Laplace reference is about 4 times faster than the normal and 35 times faster than the Merton reference.
- On lab data the smiles change little after halving the strikes; the smoothing spline does not interpolate the data.
- On S&P 500 data, calendar arbitrage appears only in far extrapolation.

## Limits and caveats
- The maturity-interpolated surface is not arbitrage-free by construction; it relies on post-processing.
- The reference distribution strongly shapes the extrapolation.

## Use in this study
- [[paper#Introduction]]: part of the surface-construction literature that motivates working in total-variance space.
- [[paper#Literature Review]]: arbitrage-free interpolation from finitely many strikes and maturities.
- [[paper#Literature Review]]: dense surfaces must be reconstructed from finitely many quotes.
- [[paper#Models]]: interpolation across maturities in total variance.
