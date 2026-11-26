---
aliases:
  - "Gonçalves and Guidolin (2006)"
title: "Predictable Dynamics in the S&P 500 Index Options Implied Volatility Surface"
authors:
  - "Sílvia Gonçalves"
  - "Massimo Guidolin"
year: 2006
venue: "Journal of Business"
doi: "10.1086/500686"
status: cited
pdf: "[[lit_review/EBSCO-FullText-04_08_2026.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options"
sample_period: "3 January 1992 to 28 June 1996"
forecast_object: "implied volatilities and option prices across the surface, via five daily cross-sectional coefficients"
horizon: "1 trading day"
methods:
  - "daily cross-sectional regression of log implied volatility on moneyness and maturity terms"
  - "VAR on the five coefficients, lags by BIC"
benchmarks:
  - "random walk for the coefficients (ad hoc straw man)"
  - "random walk for implied volatilities"
  - "Heston-Nandi NGARCH(1,1)"
  - "AR(1) for log implied volatility"
evaluation_design: "four expanding estimation windows, each followed by a six-month prediction window; Diebold-Mariano tests; simulated delta-hedged trading with transaction costs"
loss_metrics:
  - "RMSE and MAE in implied volatility and in option prices"
  - "correct direction-of-change percentage"
  - "trading profit, Sharpe ratio, Leland's A"
headline_finding: "A VAR on daily surface coefficients beats random-walk and NGARCH forecasts one day ahead, but trading profits vanish at higher transaction costs and on broad trading rules."
tags:
  - literature
  - literature/forecasting
  - literature/surface-dynamics
---

# Gonçalves and Guidolin (2006)

**Predictable Dynamics in the S&P 500 Index Options Implied Volatility Surface.** Journal of Business 79(3): 1591-1635.

## Question
- Does modelling the time series of unstable cross-sectional surface coefficients improve forecasts, and can the gains be traded?

## Data
- Daily CBOE closing prices of S&P 500 calls and puts; 48,192 filtered observations, 41 options a day on average; absolute moneyness within 10%, six trading days to one year to expiry.

## Method
- Each day, regress log implied volatility on time-adjusted moneyness, its square, maturity and their interaction; then fit a VAR to the five coefficient series.

## Evaluation design
- Expanding estimation windows with non-overlapping prediction windows.
- $1,000 a day in delta-hedged positions under four trading rules, with fixed costs, filters and imputed bid-ask spreads.

## Findings
- Out-of-sample implied-volatility RMSE: 1.43% (VAR), 2.30% (coefficient random walk), 2.07% (NGARCH), 1.49% (implied-volatility random walk); price RMSE $1.00, $1.75, $1.71, $1.64.
- Gains come mainly from short- and medium-term out-of-the-money and at-the-money contracts.
- Under the broad filter rule, profits are significant at $0.125, insignificant at $0.25 and negative at $0.50 per contract; the most selective rule stays profitable.

## Limits and caveats
- No no-arbitrage restrictions; prices come from Black-Scholes with forecast volatilities; accuracy decays faster than the benchmarks' at 2-5 days.

## Use in this study
- [[paper#Abstract]]: early coefficient-based SPX surface forecasting, the start of the pattern the headline extends.
- [[paper#Introduction]]: statistical predictability without robust economic gains.
- [[paper#Literature Review]]: VAR on daily surface coefficients; economic value fragile to trading costs.
- [[paper#Conclusion]]: simple low-dimensional linear models capture surface dynamics.
