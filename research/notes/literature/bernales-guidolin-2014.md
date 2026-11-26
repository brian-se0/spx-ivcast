---
aliases:
  - "Bernales and Guidolin (2014)"
title: "Can we forecast the implied volatility surface dynamics of equity options? Predictability and economic value tests"
authors:
  - "Alejandro Bernales"
  - "Massimo Guidolin"
year: 2014
venue: "Journal of Banking & Finance"
doi: "10.1016/j.jbankfin.2014.06.002"
status: cited
pdf: "[[lit_review/1-s2.0-S037842661400199X-main.pdf]]"
pdf_version: published
asset_class: "US individual equity options (150 names) and S&P 500 index options"
sample_period: "4 January 1996 to 29 December 2006"
forecast_object: "implied volatilities and option prices across each stock's surface, via five daily surface coefficients"
horizon: "1 day (also 3, 5, 7 and 9 days)"
methods:
  - "daily GLS regression of log implied volatility on moneyness and maturity terms"
  - "VARX on equity surface coefficients with S&P 500 surface coefficients as exogenous regressors"
benchmarks:
  - "VAR on equity surface coefficients only"
  - "random walk for the coefficients (ad hoc Strawman)"
  - "Duan-Simonato American option GARCH"
  - "random walk for implied volatilities"
evaluation_design: "recursive daily estimation on six-month rolling windows; Diebold-Mariano tests; simulated straddle and delta-hedged trading before and after transaction costs"
loss_metrics:
  - "RMSE"
  - "MAE"
  - "mean correct prediction of direction of change"
  - "trading profit, Sharpe ratio, factor-model alpha"
headline_finding: "Equity-option surfaces are statistically predictable, best when S&P 500 surface dynamics are included, but trading profits disappear once transaction costs are counted."
tags:
  - literature
  - literature/forecasting
  - literature/surface-dynamics
---

# Bernales and Guidolin (2014)

**Can we forecast the implied volatility surface dynamics of equity options? Predictability and economic value tests.** Journal of Banking & Finance 46: 326-342.

## Question
- Are individual stocks' implied-volatility surfaces predictable, and does the S&P 500 surface help forecast them?

## Data
- OptionMetrics daily closing bid-ask midpoints for the 150 equity options with the highest average volume, plus S&P 500 options; moneyness 0.9 to 1.1, six trading days to one year to expiry.

## Method
- Daily cross-sectional model of log implied volatility in time-adjusted moneyness, its square, maturity and their interaction, for each stock and the index; then a VARX for each stock's five coefficients.

## Evaluation design
- One-day-ahead forecasts in volatility and price space, averaged over the 150 names.
- $1,000 daily at-the-money straddle and delta-hedged portfolios; costs set at half the quoted spread.

## Findings
- Implied-volatility RMSE: 0.039 (VARX), 0.046 (VAR), 0.059 (coefficient random walk), 0.053 (GARCH), 0.049 (implied-volatility random walk).
- The VARX leads at every horizon to nine days.
- Before costs, straddle portfolios earn 4.42% a day on average; after costs, profits are negative for every model and every stock.

## Limits and caveats
- The sample stops in 2006 to exclude the 2007-2009 turmoil.
- Next-day stock prices and rates are set to today's values.

## Use in this study
- [[paper#Literature Review]]: coefficient-based surface forecasting extended to individual equity options, with statistical predictability kept separate from net economic gains.
