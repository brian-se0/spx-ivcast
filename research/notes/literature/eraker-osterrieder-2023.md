---
aliases:
  - "Eraker and Osterrieder (2023)"
title: "Market Maker Inventory, Bid-Ask Spreads, and the Computation of Option Implied Risk Measures"
authors:
  - "Bjørn Eraker"
  - "Daniela Osterrieder"
year: 2023
venue: "Journal of Financial Econometrics"
doi: "10.1093/jjfinec/nbac025"
status: uncited
pdf: "[[lit_review/nbac025.pdf]]"
pdf_version: published
asset_class: "SPX index options"
sample_period: "2 January 1998 to 29 August 2014 (4192 daily observations)"
forecast_object: "not a forecasting paper (bias in option-implied risk measures)"
horizon: "not applicable"
methods:
  - "market-maker inventory model with asymmetric bid-ask spreads"
  - "bias-corrected option quotes"
benchmarks:
  - "option-implied risk measures computed from mid-quotes"
evaluation_design: "not applicable"
loss_metrics: []
headline_finding: "Mid-quotes overstate fear and risk premia tied to the centre of the return distribution and understate tail-event risk relative to bias-corrected quotes."
tags:
  - literature
  - literature/microstructure
  - literature/surface-construction
---

# Eraker and Osterrieder (2023)

**Market Maker Inventory, Bid-Ask Spreads, and the Computation of Option Implied Risk Measures.** J. Financ. Econom. 21(5): 1820-1851.

## Question
- How do bid-ask spreads and market-maker inventory distort option-implied risk measures computed from mid-quotes?

## Data
- Daily SPX option data, 1998-2014, plus a second dataset of SPX option holdings of firms and retail customers.

## Method
- Reduced-form evidence on spread determinants and a market-making model; estimates give bias-corrected quotes used to compute several option-implied risk measures.

## Evaluation design
- Not applicable.

## Findings
- Asking prices react more to shocks than bids; centre and jump-related premia are overstated with mid-quotes, tail risk is larger after correction.

## Limits and caveats
- Not stated in the parts read.

## Use in this study
Relevant to input quality: mid-quote noise affects any implied-volatility surface built from SPX option quotes.
