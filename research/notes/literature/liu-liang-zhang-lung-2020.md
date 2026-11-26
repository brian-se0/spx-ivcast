---
aliases:
  - "Liu, Liang, Zhang and Lung (2020)"
title: "Implied volatility forecast and option trading strategy"
authors:
  - "Dehong Liu"
  - "Yucong Liang"
  - "Lili Zhang"
  - "Peter Lung"
  - "Rizwan Ullah"
year: 2020
venue: "International Review of Economics and Finance"
doi: "10.1016/j.iref.2020.10.023"
status: uncited
pdf: "[[lit_review/Implied volatility forecast and option trading strategy -- Liu, Dehong; Liang, Yucong; Zhang, Lili; Lung, Peter; Ullah, -- International Review of -- 10_1016_j_iref_2020_10_023 -- e1165de3d78078d85d85a6d52dd9f9ac -- Ann.pdf]]"
pdf_version: accepted-manuscript
asset_class: "S&P 500 index options"
sample_period: "January 8, 2013 to May 29, 2018; out-of-sample January 2017 to May 2018"
forecast_object: "implied volatility (VIX used as the training target)"
horizon: "not stated"
methods:
  - "ABC-BP neural network (Artificial Bee Colony with back propagation)"
  - "Monte Carlo simulation and straddle trading strategy"
benchmarks:
  - "BP neural network"
  - "Black-Scholes model"
  - "GARCH (robustness)"
evaluation_design: "out-of-sample test January 2017 to May 2018"
loss_metrics:
  - "MSE"
  - "MAE"
  - "MBE"
headline_finding: "The ABC-BP network has the smallest MSE, MAE and MBE among the three models compared."
tags:
  - literature
  - literature/forecasting
  - literature/machine-learning
---

# Liu, Liang, Zhang and Lung (2020)

**Implied volatility forecast and option trading strategy.** International Review of Economics and Finance (journal pre-proof).

## Question
- Does an improved neural network predict implied volatility better, and can forecasts support straddle trading?

## Data
- Bloomberg daily S&P 500 option data, filtered by volume, price and delta.

## Method
- ABC-BP network trained on VIX; Monte Carlo option prices feed a straddle strategy.

## Evaluation design
- Out-of-sample comparison Jan 2017 to May 2018.

## Findings
- Monte Carlo prices are more efficient for the straddle strategy; the network beats GARCH in a robustness test.

## Limits and caveats
- Forecasts a single volatility series, not the surface.

## Use in this study
Relates as an earlier neural-network implied-volatility forecast and trading application, but only for a scalar series.
