---
aliases:
  - "Olsen, Djupskås, de Lange, and Risstad (2025)"
title: "Forecasting implied volatilities of currency options with machine learning techniques and econometrics models"
authors:
  - "Asbjørn Olsen"
  - "Gard Djupskås"
  - "Petter Eilif de Lange"
  - "Morten Risstad"
year: 2025
venue: "International Journal of Data Science and Analytics"
doi: "10.1007/s41060-024-00528-7"
status: cited
pdf: "[[lit_review/s41060-024-00528-7.pdf]]"
pdf_version: published
asset_class: "EURUSD FX options"
sample_period: "2 January 2007 to 31 August 2021 (test September 2018 to August 2021)"
forecast_object: "daily implied volatility of 55 delta-maturity series, each modelled separately"
horizon: "not stated"
methods:
  - "LSTM"
benchmarks:
  - "AR(1)-GARCH(1,1)"
  - "random forest"
  - "HAR"
  - "MIDAS"
evaluation_design: "single chronological split; 60:20:20 for the LSTM and 80:20 for the benchmarks; 599 test observations"
loss_metrics:
  - "MSE"
  - "RMSE"
  - "MAE"
  - "MAPE"
headline_finding: "LSTM is the best model at the shortest maturities and AR(1)-GARCH(1,1) at maturities of three months and longer, by small margins."
tags:
  - literature
  - literature/volatility-forecasting
  - literature/machine-learning
---

# Olsen, Djupskås, de Lange, and Risstad (2025)

**Forecasting implied volatilities of currency options with machine learning techniques and econometrics models.** International Journal of Data Science and Analytics 20: 1329-1347.

## Question
- Does an LSTM forecast EURUSD implied volatility across the surface better than random forest and time-series models?

## Data
- Bloomberg daily implied volatilities, 02.01.2007 to 31.08.2021: 55 series (put and call deltas 5 to 35 plus an at-the-money put; maturities one week to one year), 2994 observations each.

## Method
- Each series is modelled on its own with an LSTM, AR(1)-GARCH(1,1), random forest, HAR and MIDAS; GARCH extensions add GJR, moving-average and Student's t terms.

## Evaluation design
- LSTM: training January 2007 to October 2015, validation to September 2018, test September 2018 to August 2021; Diebold-Mariano tests.

## Findings
- One week: LSTM beats AR-GARCH by 0.75% in RMSE on average; the authors state that AR-GARCH is not significantly poorer at shorter maturities.
- One month: AR-GARCH is on average 0.78% better in RMSE, LSTM 1.56% better in MAE.
- Three months and longer: AR(1)-GARCH(1,1) is superior at all moneyness levels, with no statistically significant differences.
- With other GARCH specifications and residual distributions, the AR-GARCH framework outperforms the machine-learning models for all options.

## Limits and caveats
- The surface is not modelled jointly; there is one test window, which contains the COVID-19 shock.

## Use in this study
- [[paper#Literature Review]]: model rankings depend on maturity, with LSTM ahead at the short end of EURUSD implied volatilities and AR-GARCH ahead further out, by small margins; at the short end AR-GARCH is not significantly poorer than LSTM.
