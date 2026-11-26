---
aliases:
  - "Vitali, Kopa and Giana (2023)"
title: "Implied volatility smoothing at COVID-19 times"
authors:
  - "Sebastiano Vitali"
  - "Miloš Kopa"
  - "Gabriele Giana"
year: 2023
venue: "Computational Management Science"
doi: "10.1007/s10287-023-00465-z"
status: uncited
pdf: "[[lit_review/s10287-023-00465-z.pdf]]"
pdf_version: published
asset_class: "options on five equity indexes (S&P500, HangSeng, EuroStoxx50, DAX, FTSEMib) and five stocks"
sample_period: "options with maturities December 2019 to June 2020"
forecast_object: "not a forecasting paper (shape of the implied volatility smile during COVID-19)"
horizon: "quotes 15 and 30 days before maturity"
methods:
  - "semi-parametric kernel smoothing with no-arbitrage conditions"
  - "local polynomial smoothing"
benchmarks: []
evaluation_design: "not applicable"
loss_metrics: []
headline_finding: "Smoothed implied volatility functions show sudden and massive shape changes in several cases during the pandemic."
tags:
  - literature
  - literature/surface-construction
  - literature/no-arbitrage
---

# Vitali, Kopa and Giana (2023)

**Implied volatility smoothing at COVID-19 times.** Comput. Manag. Sci. 20: 32.

## Question
- How did the pandemic change the shape of implied volatility smiles?

## Data
- Index and single-stock options with seven monthly maturities, quoted 15 and 30 days before expiry.

## Method
- Kernel-based semi-parametric smoothing of liquid options under no-arbitrage conditions.

## Evaluation design
- Descriptive comparison across months.

## Findings
- Sudden, large shape changes in several smiles.

## Limits and caveats
- Single-maturity smiles; no dynamics model.

## Use in this study
Relevant to no-arbitrage smoothing of index smiles, including S&P500, and to regime shifts in smile shape.
