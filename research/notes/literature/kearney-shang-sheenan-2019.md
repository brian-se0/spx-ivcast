---
aliases:
  - "Kearney, Shang, and Sheenan (2019)"
title: "Implied volatility surface predictability: The case of commodity markets"
authors:
  - "Fearghal Kearney"
  - "Han Lin Shang"
  - "Lisa Sheenan"
year: 2019
venue: "Journal of Banking and Finance"
doi: "10.1016/j.jbankfin.2019.105657"
status: cited
pdf: "[[lit_review/1-s2.0-S0378426619302328-main.pdf]]"
pdf_version: published
asset_class: "Options on 12 commodity futures (agricultural, energy, precious metals)"
sample_period: "January 2006-December 2016"
forecast_object: "Implied-volatility surface of each commodity option, by moneyness and time to maturity"
horizon: "1, 2, 5, 10 and 30 days"
methods:
  - "Goncalves-Guidolin parametric surface (GG) with AR, VAR, ARIMA or ETS coefficient forecasts"
  - "Chalamandaris-Tsekrekos Nelson-Siegel surface (CT) with AR, VAR, ARIMA or ETS coefficient forecasts"
  - "Regression tree (RT)"
benchmarks:
  - "No-change random walk in the fitted coefficients (GG-RW, CT-RW)"
evaluation_design: "Rolling out-of-sample: fixed 1,167-day window, 500 out-of-sample days (December 2014-December 2016)"
loss_metrics:
  - "RMSE"
  - "RMSPE"
  - "MAPE"
  - "Sign success ratio"
headline_finding: "No model class wins across all commodities; the Nelson-Siegel term-structure model is most accurate for energy and precious metals options, and regression trees look best for agricultural options."
tags:
  - literature
  - literature/forecasting
  - literature/evaluation
---

# Kearney, Shang, and Sheenan (2019)

**Implied volatility surface predictability: The case of commodity markets.** Journal of Banking and Finance 108: 105657.

## Question
- Do the latent-factor and parametric surface-forecasting frameworks used for equity, index, currency and interest-rate options find predictable patterns in commodity-option surfaces?

## Data
- Daily implied-volatility quotes from ivolatility.com for options on 12 commodity futures: seven agricultural, three energy, plus gold and silver. Copper is dropped after filtering.
- Traded contracts only (volume > 0), moneyness 90-110%, maturities from one month to two years.

## Method
- GG and CT cross-sections are fitted each day; their coefficients are then forecast with AR, VAR, ARIMA or exponential smoothing. CT adds Nelson-Siegel term-structure factors and separate left and right smile terms.
- A pruned regression tree on moneyness and maturity is the machine-learning alternative.

## Evaluation design
- In-sample January 2006-December 2014; 500 rolling out-of-sample days with direct multi-day forecasts.
- Model confidence set (Hansen, Lunde and Nason) on squared error at 75% confidence, range statistic, 5,000 block-bootstrap samples, 11 candidate models per commodity.

## Findings
- GG performs poorly overall. CT is most accurate for energy and precious metals; RT is most promising for agricultural options.
- One day ahead, random-walk benchmarks sit in the superior set alongside time-series models for five commodities; at five days, for two.
- For long maturities, CT-RW is more accurate than the time-series versions on RMSE.

## Limits and caveats
- No trading or hedging exercise; economic exploitation is left to future work.
- The no-change benchmark holds fitted coefficients constant rather than the observed surface.
- Results for 2- and 10-day horizons are not tabulated.

## Use in this study
- [[paper#Introduction]]: cited for random-walk or no-change benchmarks being serious comparators at a one-session horizon.
- [[paper#Literature Review]]: cited for Nelson-Siegel term-structure factors giving the most accurate rolling out-of-sample forecasts for energy and precious-metals options, with no single class of model ahead across all commodities.
- [[paper#Literature Review]]: cited as a surface study that addresses multiple comparisons in rolling forecasts.
- [[paper#Walk-Forward Design, Tuning, and Evaluation]]: cited as precedent for the model confidence set with the range statistic.
