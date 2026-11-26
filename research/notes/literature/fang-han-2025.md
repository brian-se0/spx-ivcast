---
aliases:
  - "Fang and Han (2025)"
title: "Realized GARCH Model in Volatility Forecasting and Option Pricing"
authors:
  - "Zheng Fang"
  - "Jae-Young Han"
year: 2025
venue: "Computational Economics"
doi: "10.1007/s10614-024-10826-8"
status: uncited
pdf: "[[lit_review/s10614-024-10826-8.pdf]]"
pdf_version: published
asset_class: "S&P 500, Nasdaq and Dow Jones Industrial Average indices; European options on the S&P 500"
sample_period: "not stated"
forecast_object: "realized volatility and option prices"
horizon: "not stated"
methods:
  - "realized GARCH with additive cascade model of volatility components"
  - "Monte Carlo option pricing under martingale measures"
benchmarks: []
evaluation_design: "not stated"
loss_metrics:
  - "MSE"
  - "QLIKE"
headline_finding: "A realized-volatility forecasting model that captures long-range persistence is adapted into a discrete-time stochastic volatility option pricing method."
tags:
  - literature
  - literature/volatility-forecasting
---

# Fang and Han (2025)

**Realized GARCH Model in Volatility Forecasting and Option Pricing.** Comput. Econ. 66: 3637-3657.

## Question
- Can a realized-volatility model that combines GARCH with an additive cascade of frequency components both forecast volatility and price options?

## Data
- S&P 500, Nasdaq and DJIA indices; S&P 500 European options.

## Method
- GARCH conditional volatility plus cascade components; martingale measures and prices from Monte Carlo.

## Evaluation design
- Not stated in the parts read; MSE and QLIKE are discussed as robust losses.

## Findings
- Forecasts have reduced measurement error and reproduce the volatility time-series pattern.

## Limits and caveats
- Not stated in the parts read.

## Use in this study
Not directly related: model-based option pricing from realized-volatility forecasts, not forecasting the implied-volatility surface.
