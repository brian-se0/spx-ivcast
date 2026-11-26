---
aliases:
  - "Shang and Kearney (2022)"
title: "Dynamic functional time-series forecasts of foreign exchange implied volatility surfaces"
authors:
  - "Han Lin Shang"
  - "Fearghal Kearney"
year: 2022
venue: "International Journal of Forecasting (PDF on file is the arXiv preprint arXiv:2107.14026v1)"
doi: "10.1016/j.ijforecast.2021.07.011"
status: cited
pdf: "[[lit_review/2107.14026v1.pdf]]"
pdf_version: preprint
asset_class: "EUR-USD, EUR-GBP and EUR-JPY OTC currency options; SPX index options as a robustness check"
sample_period: "January 1, 2008-December 30, 2016 (currency options); January 2013-December 2019 (SPX check)"
forecast_object: "Daily implied-volatility smiles over five deltas at 1-month, 6-month and 2-year maturities, treated as functional time series"
horizon: "1, 5 and 10 days"
methods:
  - "Univariate functional time series (FPCA with ARIMA score forecasts)"
  - "Multivariate functional time series"
  - "Multilevel functional time series"
  - "Dynamic FPCA based on the long-run covariance, applied to each of the three"
benchmarks:
  - "Random walk"
  - "AR(1)"
  - "Chalamandaris and Tsekrekos (2011)"
  - "Goncalves and Guidolin (2006)"
evaluation_design: "Expanding window re-estimated daily; 522 one-step-ahead forecasts from January 1, 2015 to December 30, 2016"
loss_metrics:
  - "MAFE"
  - "MSFE"
  - "MME(U)"
  - "MME(O)"
headline_finding: "Dynamic functional principal components generally improve out-of-sample accuracy, most for the univariate method, while random-walk and AR(1) benchmarks are hard to beat at short horizons."
tags:
  - literature
  - literature/forecasting
  - literature/surface-dynamics
---

# Shang and Kearney (2022)

**Dynamic functional time-series forecasts of foreign exchange implied volatility surfaces.** arXiv preprint arXiv:2107.14026v1 [q-fin.ST], 22 Jul 2021.

## Question
- Do dynamic, multivariate and multilevel functional time-series methods forecast currency-option implied-volatility surfaces better than static functional methods and standard benchmarks?

## Data
- Bloomberg contributed quotes for three euro currency pairs at deltas 10, 25, 50, 75 and 90 and three maturities.
- SPX robustness check: 97 daily curves at 30 and 60 days to expiry, 20 for testing.

## Method
- Each maturity's smile is a curve; components are kept to 99% cumulative variance or K = 4, and scores are forecast with ARIMA.
- Dynamic variants extract components from the estimated long-run covariance.

## Evaluation design
- 1,827 initial observations to December 31, 2014; 522 one-day, 518 five-day and 513 ten-day forecasts.
- Model confidence set at 95% on MAFE, with T_max and T_R statistics.

## Findings
- For the EUR-USD data shown, two components explain at least 99% of total variance or long-run covariance.
- The dynamic univariate method is in the superior set in 13 of 35 cases (T_max).
- RW and AR(1) are "quite hard to beat" for short-term forecasts; functional methods gain at longer horizons.
- A stylised straddle strategy earns significantly positive returns for EUR-USD and EUR-GBP, not EUR-JPY.

## Limits and caveats
- Three maturities and five deltas only.
- The trading exercise leaves out liquidity, margin, slippage and other frictions.

## Use in this study
- [[paper#Introduction]]: random-walk or no-change benchmarks as serious one-session comparators.
- [[paper#Introduction]]: random-walk benchmarks hard to beat at short horizons.
- [[paper#Introduction]]: a few factors or functional principal components capture much of the surface dynamics.
- [[paper#Literature Review]]: dynamic functional principal component forecasts of foreign-exchange surfaces under expanding-window evaluation.
- [[paper#Literature Review]]: expanding-window design paired with the model confidence set.
- [[paper#Literature Review]]: stylised trading strategy alongside statistical comparisons.
- [[paper#Feature Engineering and Targets]]: persistent, low-dimensional surface dynamics behind the lagged-surface features.
- [[paper#Walk-Forward Design, Tuning, and Evaluation]]: precedent for the model confidence set with the range statistic.
