---
aliases:
  - "Wiedemann, Jacquier, and Gonon (2025)"
  - "Wiedemann et al. (2025)"
title: "Operator Deep Smoothing for Implied Volatility"
authors:
  - "Ruben Wiedemann"
  - "Antoine Jacquier"
  - "Lukas Gonon"
year: 2025
venue: "ICLR 2025 (conference paper); arXiv:2406.11520v3"
doi: "10.48550/arXiv.2406.11520"
status: cited
pdf: "[[lit_review/2406.11520v3.pdf]]"
pdf_version: preprint
asset_class: "S&P 500 index options (CBOE intraday quotes); end-of-day SPX, NDX, DJX and RUT index options for generalization"
sample_period: "2012-2021"
forecast_object: "not a forecasting paper; smoothed implied volatility surface built from contemporaneous quotes (nowcasting)"
horizon: "not applicable"
methods:
  - "Interpolating graph neural operator trained with a fitting loss, calendar and butterfly arbitrage penalties and smoothness regularization"
benchmarks:
  - "SVI calibrated slice by slice"
  - "Deep smoothing of Ackerer et al. (2020)"
evaluation_design: "train 2012-2020 with 750 random validation surfaces, test 2021 with monthly finetuning; generalization check on January 2021 end-of-day data for four US indices"
loss_metrics:
  - "MAPE (surface-average absolute relative error)"
  - "price error relative to the bid-ask spread"
  - "calendar and butterfly arbitrage losses"
headline_finding: "A single graph neural operator with about 100 thousand parameters smooths ten years of intraday S&P 500 implied volatility data with a test MAPE of around 0.5%, against 1% to 2% for SVI."
tags:
  - literature
  - literature/surface-construction
  - literature/machine-learning
---

# Wiedemann, Jacquier, and Gonon (2025)

**Operator Deep Smoothing for Implied Volatility.** Published as a conference paper at ICLR 2025; arXiv:2406.11520v3.

## Question
- Can one trained network map raw option quotes of any number and location directly to a smooth implied volatility surface, replacing instance-by-instance calibration?

## Data
- CBOE S&P 500 index option quotes at 20-minute intervals, 2012 to 2021: 49089 surfaces, just above 60 million volatility points.
- OptionMetrics end-of-day data for SPX, NDX, DJX and RUT, January 2021.

## Method
- Smoothing is cast as learning the identity operator on a function space; a graph neural operator with a purely non-local first layer produces output at arbitrary locations.
- Loss: vega-weighted relative fitting error, penalties for butterfly and calendar arbitrage, and smoothness regularization.
- 102529 trainable parameters.

## Evaluation design
- Training on 2012 to 2020 (43442 surfaces), 750 validation surfaces, testing on 2021 (4897 surfaces).
- Test months are evaluated in sequence, with finetuning after each.
- The Ackerer et al. (2020) backtest is rerun on January to April 2018 end-of-day SPX data.

## Findings
- With monthly finetuning, MAPE is around 0.5%; SVI fluctuates between 1% and 2%.
- Mean spread-relative error on the test set is 1.265, against 3.382 for SVI.
- Averaged over the test set, the arbitrage terms stay positive; on end-of-day data for other indices the output is called "virtually arbitrage-free".
- In the extrapolation test setting, median MAPE is 0.9% against 1.7% for Ackerer et al.

## Limits and caveats
- No-arbitrage conditions enter through loss penalties; end-of-day butterfly losses are small but not zero (6.41e-05 for SPX).
- Parameters are not interpretable.
- The intraday training data are proprietary; training on lower-frequency data may perform worse.
- The SVI benchmark ignores the calendar arbitrage condition.

## Use in this study
- [[paper#Literature Review]]: example of smoothing or completion treated as a modeling problem of its own, with a learned operator mapping irregular quotes to a surface.
- [[paper#Literature Review]]: cited again, for full surfaces, in support of the point that dense-surface recovery is a substantive modelling task.
