---
aliases:
  - "Avellaneda, Healy, Papanicolaou and Papanicolaou (2020)"
title: "PCA for Implied Volatility Surfaces"
authors:
  - "M. Avellaneda"
  - "B. Healy"
  - "A. Papanicolaou"
  - "G. Papanicolaou"
year: 2020
venue: "arXiv:2002.00085v1 [q-fin.ST]"
doi: ""
status: uncited
pdf: "[[lit_review/2002.00085v1.pdf]]"
pdf_version: preprint
asset_class: "U.S. equity options (500 S&P 500 constituents)"
sample_period: "2012-2017"
forecast_object: "not a forecasting paper (factor structure of implied-volatility returns)"
horizon: "not applicable"
methods:
  - "matrix PCA"
  - "tensor PCA"
  - "random matrix theory"
benchmarks: []
evaluation_design: "in-sample factor analysis"
loss_metrics: []
headline_finding: "Implied-volatility returns have about 9 significant factors, with a market factor given by an open-interest and vega weighted index."
tags:
  - literature
  - literature/surface-dynamics
---

# Avellaneda, Healy, Papanicolaou and Papanicolaou (2020)

**PCA for Implied Volatility Surfaces.** arXiv:2002.00085v1.

## Question
- How many factors drive co-movement of equity implied volatilities, and what is the market factor?

## Data
- OptionMetrics surfaces: daily, 500 names, 8 maturities, 7 strikes, 2012-2017.

## Method
- PCA of normalized implied-volatility returns, plus tensor PCA over time, name, maturity and strike.

## Evaluation design
- In-sample spectral analysis; tensor-portfolio returns shown in-sample.

## Findings
- Nine significant factors in the flattened data; the leading factor tracks an OI-Vega weighted index.

## Limits and caveats
- Single-name equity options, not the SPX surface; no out-of-sample forecasts.

## Use in this study
Relates to low-dimensional factor structure of implied-volatility movements, which motivates factor-based surface models, but it does not forecast.
