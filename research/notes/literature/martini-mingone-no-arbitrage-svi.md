---
aliases:
  - "Martini and Mingone, No arbitrage SVI"
title: "No arbitrage SVI"
authors:
  - "Claude Martini"
  - "Arianna Mingone"
year: 2021
venue: "arXiv preprint arXiv:2005.03340v2 [q-fin.MF]"
doi: ""
status: uncited
pdf: "[[lit_review/2005.03340v2.pdf]]"
pdf_version: preprint
asset_class: "DJX, SPX and NDX equity index options (CBOE); model-generated SVI smiles"
sample_period: "not stated"
forecast_object: "not a forecasting paper; characterizes SVI total-variance smiles without butterfly arbitrage"
horizon: "not applicable"
methods:
  - "Rescaled (normalized) SVI parametrization"
  - "Fukasawa necessary conditions and the Durrleman condition"
  - "Bounded least-squares calibration over the no-arbitrage domain"
benchmarks:
  - "Gatheral-Jacquier arbitrage-free parameters for the Axel Vogt example"
evaluation_design: "not applicable (in-sample calibration)"
loss_metrics:
  - "Frobenius relative error of total variances"
headline_finding: "Necessary and sufficient conditions for no butterfly arbitrage in a five-parameter SVI smile are obtained as range conditions on rescaled parameters, turning the no-arbitrage domain into a product of intervals."
tags:
  - literature
  - literature/no-arbitrage
  - literature/surface-construction
---

# Martini and Mingone, No arbitrage SVI

**No arbitrage SVI.** arXiv:2005.03340v2 [q-fin.MF], dated May 26, 2021.

## Question
- For which parameters (a, b, ρ, m, σ) is a single SVI total-variance smile free of butterfly arbitrage?

## Data
- Model-generated SVI total variances on 13 log-forward strikes, including the Axel Vogt parameters.
- CBOE daily files with bid and ask prices for DJX, SPX and NDX index options; dates not stated.

## Method
- Rescales SVI with α = a/σ, μ = m/σ and l = (k − m)/σ, so the Durrleman function splits into G1 + G2/(2σ) with G1 and G2 independent of σ.
- Fukasawa's necessary condition requires G1 > 0, giving a threshold on α and an interval for μ; the remaining condition is a lower bound on σ.
- Three functions are evaluated by root finding; calibration is bounded least squares on total variances.

## Evaluation design
- In-sample fits only.

## Findings
- Theorems 6.2 and 6.3: no butterfly arbitrage requires b(1 ± ρ) ≤ 2 and holds exactly when α exceeds a threshold F(b, ρ), μ lies in an explicit interval and σ ≥ σ*(α, b, ρ, μ).
- The domain maps to a hyperrectangle, giving a membership test with four failure types and a calibration routine.
- For the Vogt parameters the arbitrage-free fit has relative error 0.022, against 0.133 for the Gatheral-Jacquier parameters.
- Market fits are described as excellent.

## Limits and caveats
- One smile at a time: calendar-spread arbitrage between SVI slices of different maturities is left open.
- Some properties are conjectured rather than proven.
- Four-parameter sub-SVI families are named as pending work.

## Use in this study
Gives exact slice-level butterfly-arbitrage conditions for SVI total-variance smiles, background for the static-arbitrage diagnostics applied to forecast SPX surfaces; it does not address forecasting.
