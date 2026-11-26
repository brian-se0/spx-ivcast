---
aliases:
  - "Fengler, Hardle and Mammen (2007)"
title: "A Semiparametric Factor Model for Implied Volatility Surface Dynamics"
authors:
  - "Matthias R. Fengler"
  - "Wolfgang K. Härdle"
  - "Enno Mammen"
year: 2007
venue: "Journal of Financial Econometrics"
doi: "10.1093/jjfinec/nbm005"
status: uncited
pdf: "[[lit_review/nbm005.pdf]]"
pdf_version: published
asset_class: "DAX index options"
sample_period: "January 1998 to May 2001"
forecast_object: "implied volatility surface dynamics via a low-dimensional latent factor time series"
horizon: "not stated"
methods:
  - "semiparametric factor model"
  - "VAR on factor loadings"
benchmarks:
  - "standard principal component analysis of the surface"
evaluation_design: "not stated"
loss_metrics:
  - "portion of variance explained"
headline_finding: "Three basis functions explain 97% of surface variation, and the loading series are modelled with a VAR in levels."
tags:
  - literature
  - literature/surface-dynamics
---

# Fengler, Hardle and Mammen (2007)

**A Semiparametric Factor Model for Implied Volatility Surface Dynamics.** J. Financ. Econom. 5(2): 189-218.

## Question
- How can the implied volatility surface (IVS) be approximated by a few factors despite its degenerate design (data only on a few maturity strings)?

## Data
- DAX option implied volatilities, Jan 1998 to May 2001, in moneyness and time-to-maturity.

## Method
- Factor model with smooth basis functions fitted locally around design points; time-varying loadings are modelled with vector autoregressions.

## Evaluation design
- Not stated.

## Findings
- L = 1, 2, 3 basis functions explain up to 89%, 94% and 97% of variation; L = 3 is chosen. ADF tests give weak evidence of a unit root in two loadings, and a VAR in levels is preferred.

## Limits and caveats
- Validity of VAR on estimated rather than true loadings is argued, with a conjecture for kernel smoothing.

## Use in this study
Early factor-model account of IVS dynamics, a direct precursor to factor-based surface forecasting.
