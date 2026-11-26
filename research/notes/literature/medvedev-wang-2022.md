---
aliases:
  - "Medvedev and Wang (2022)"
title: "Multistep forecast of the implied volatility surface using deep learning"
authors:
  - "Nikita Medvedev"
  - "Zhiguang Wang"
year: 2022
venue: "Journal of Futures Markets"
doi: "10.1002/fut.22302"
status: cited
pdf: "[[lit_review/Journal of Futures Markets - 2022 - Medvedev - Multistep forecast of the implied volatility surface using deep learning.pdf]]"
pdf_version: published
asset_class: "S&P 500 index (SPX) options"
sample_period: "2002-01-02 to 2019-12-31 (test 2019-08-19 to 2019-12-31)"
forecast_object: "implied volatility on 20 log-moneyness bins by 4 quarterly contract months"
horizon: "1, 30, 60 and 90 days"
methods:
  - "ConvLSTM"
  - "LSTM"
benchmarks:
  - "VAR"
  - "VEC"
evaluation_design: "single chronological split with a 90-trading-day holdout; no re-estimation in the test period"
loss_metrics:
  - "RMSE"
  - "MAPE"
headline_finding: "ConvLSTM has the lowest out-of-sample RMSE and MAPE at every reported horizon, while LSTM is less accurate than the VAR and VEC benchmarks."
tags:
  - literature
  - literature/forecasting
  - literature/machine-learning
---

# Medvedev and Wang (2022)

**Multistep forecast of the implied volatility surface using deep learning.** Journal of Futures Markets 42(4): 645-667.

## Question
- Can LSTM and ConvLSTM networks beat traditional time-series models in multistep out-of-sample forecasts of the whole SPX surface?

## Data
- Delta Neutral end-of-day SPX option quotes; March, June, September and December expiries; 20 log-moneyness bins from -0.05 to 0.05, with missing cells filled by linear interpolation.

## Method
- Both networks map a 30-day history to a 30-day forecast of all 80 series; VAR and VEC are the benchmarks.

## Evaluation design
- Training 2002-01-02 to 2019-08-16; test 2019-08-19 to 2019-12-31 (90 trading days); Diebold-Mariano test at the 1-day horizon only.

## Findings
- Average out-of-sample MAPE: ConvLSTM 8.26%, VAR 13.72%, VEC 13.75%, LSTM 18.74%.
- At horizons of 1, 30, 60 and 90 days ConvLSTM has the lowest RMSE and MAPE; LSTM is worse than VAR and VEC at each.
- In a butterfly-spread exercise over the 90-day sample, VAR and VEC earn positive returns and the two networks do not.

## Limits and caveats
- One 90-trading-day test window; the benchmark set is VAR and VEC only.
- The authors note that more tuning might make LSTM comparable to ConvLSTM.

## Use in this study
- [[paper#Introduction]]: a recent machine-learning approach (sequence model) whose gains are empirical rather than guaranteed.
- [[paper#Literature Review]]: ConvLSTM beats VAR and VEC on an interpolated SPX surface over a 90-day 2019 test period, while a plain LSTM underperforms both.
