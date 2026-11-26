---
aliases:
  - "Mingone (2022)"
title: "No arbitrage global parametrization for the eSSVI volatility surface"
authors:
  - "Arianna Mingone"
year: 2022
venue: "Quantitative Finance"
doi: "10.1080/14697688.2022.2117076"
status: cited
pdf: "[[lit_review/No arbitrage global parametrization for the eSSVI volatility surface.pdf]]"
pdf_version: published
asset_class: "TA35 index options and NIS/USD FX options"
sample_period: "calibration on 2021-10-26; arbitrage checks 2019-01-01 to 2021-10-27"
forecast_object: "not a forecasting paper; parametrizes the eSSVI total implied variance surface"
horizon: "not applicable"
methods:
  - "Global eSSVI (product-of-intervals re-parametrization of the eSSVI no-arbitrage domain)"
  - "Least-squares calibration on prices across all maturities at once"
benchmarks:
  - "Carr-Pelts-Tehranchi (CPT) price surface"
evaluation_design: "in-sample calibration fit; leave-one-maturity-out interpolation and extrapolation"
loss_metrics:
  - "Percentage of calibrated prices outside the bid-ask spread"
  - "Average absolute calibration error in basis points of the forward"
headline_finding: "A re-parametrization of eSSVI over a product of intervals makes every admissible parameter vector free of butterfly and calendar-spread arbitrage and allows joint calibration of all maturities."
tags:
  - literature
  - literature/no-arbitrage
  - literature/surface-construction
---

# Mingone (2022)

**No arbitrage global parametrization for the eSSVI volatility surface.** Quantitative Finance 22(12): 2205-2217.

## Question
- Can eSSVI be parametrized so that every admissible parameter vector is arbitrage-free, allowing all maturities to be calibrated at once instead of sequentially?

## Data
- Trades and quotes from the last 10 minutes of trading on 2021-10-26, aggregated to one price per option: TA35 index (64 calls, 107 puts) and NIS/USD (16 calls, 12 puts), provided by TASE.

## Method
- eSSVI models total implied variance with SSVI slices (θ, ρ, ψ) whose correlation may differ by maturity.
- Takes calendar-spread conditions between slices from Hendriks and Martini (2019) and butterfly conditions from Gatheral-Jacquier (sufficient) or Martini-Mingone (necessary and sufficient).
- Replaces the slice parameters by (ρ_i, θ_1, a_i, c_i) in ]-1,1[^N x ]0,∞[^N x ]0,1[^N and calibrates by squared price differences.

## Evaluation design
- In-sample fit against the CPT model; a second exercise drops each of four TA35 maturities and interpolates or extrapolates it.

## Findings
- Proposition 3.1: for any parameters in the domain, the slices are free of butterfly and calendar-spread arbitrage.
- Average absolute error in basis points of the forward: eSSVI 1.92 (TA35) and 1.29 (NIS/USD); CPT 2.19 and 1.86.
- Calibration times are reported as 10 times smaller than for CPT.

## Limits and caveats
- Built on one of two alternative sufficient calendar-spread conditions; numerical results use the sufficient-but-not-necessary Gatheral-Jacquier butterfly conditions.
- The 2-day TA35 maturity accounts for most prices outside the bid-ask spread.
- Small numerical arbitrage can arise for ρ near ±1.

## Use in this study
- [[paper#Introduction]]: part of the arbitrage-geometry literature that motivates working in total-variance space.
- [[paper#Literature Review]]: cited for re-parametrizing the eSSVI no-arbitrage domain so that all maturities can be calibrated jointly.
- [[paper#Models]]: total-variance arbitrage conditions behind forecasting total variance.
- [[paper#Models]]: reference for calling the neural model arbitrage-aware, not arbitrage-free.
