---
aliases:
  - "Patton (2011)"
title: "Volatility forecast comparison using imperfect volatility proxies"
authors:
  - "Andrew J. Patton"
year: 2011
venue: "Journal of Econometrics"
doi: "10.1016/j.jeconom.2010.03.034"
status: cited
pdf: "[[lit_review/1-s2.0-S030440761000076X-main.pdf]]"
pdf_version: published
asset_class: "IBM equity returns (empirical illustration)"
sample_period: "January 1993 to December 2003"
forecast_object: "Conditional variance of returns (latent); the paper studies which loss functions rank variance forecasts correctly"
horizon: "1 day"
methods:
  - "Analytical optimal forecasts under nine common loss functions"
  - "Necessary and sufficient conditions for a robust loss function"
  - "Homogeneous robust loss family indexed by b"
  - "Diebold-Mariano-West tests"
benchmarks: []
evaluation_design: "Theory, plus Diebold-Mariano-West tests of a 60-day rolling-window forecast against RiskMetrics on 2500 daily observations under four volatility proxies"
loss_metrics:
  - "MSE"
  - "QLIKE"
  - "MSE-LOG"
  - "MSE-SD"
  - "MSE-prop"
  - "MAE"
  - "MAE-LOG"
  - "MAE-SD"
  - "MAE-prop"
headline_finding: "Only loss functions of a specific form, which includes MSE and QLIKE, rank variance forecasts with a conditionally unbiased noisy proxy the same way as with the true conditional variance."
tags:
  - literature
  - literature/evaluation
  - literature/volatility-forecasting
---

# Patton (2011)

**Volatility forecast comparison using imperfect volatility proxies.** Journal of Econometrics 160: 246-256.

## Question

- When the conditional variance is unobservable and a noisy but conditionally unbiased proxy replaces it, which loss functions still rank competing forecasts correctly?

## Data

- Illustration: IBM daily open-to-close returns from TAQ, January 1993 to December 2003; 272 observations initialise the forecasts and 2500 are used for comparison.

## Method

- A loss is robust if the expected-loss ranking of any two forecasts is the same with the proxy as with the true variance.
- Proposition 1 gives the necessary and sufficient functional form; Proposition 4 gives the homogeneous subset, a one-parameter family in which b = 0 is MSE and b = -2 is QLIKE.
- QLIKE is defined as log h plus the proxy divided by h.

## Evaluation design

- Optimal forecasts under each loss are derived for squared-return, realised-variance and range proxies; the IBM comparison uses the robust family at five values of b with four proxies.

## Findings

- Of nine common losses, only MSE and QLIKE have the conditional variance as the optimal forecast; under normality the others give optima from about one quarter to three times the true variance.
- Less noisy proxies reduce the distortion.
- MSE is the only robust loss depending solely on the forecast error; QLIKE the only one depending solely on the standardised forecast error.
- In the IBM example only QLIKE yields a significant difference, favouring RiskMetrics.

## Limits and caveats

- Robust here does not mean robust to outliers.
- The proxy must be conditionally unbiased, and proxy noise still inflates the level of expected loss.
- Rankings of two imperfect forecasts can differ across robust losses.

## Use in this study

- [[paper#Literature Review]]: evidence that forecast rankings can be distorted when latent volatility is evaluated with imperfect proxies, and source of the robust loss class that includes QLIKE.
- [[paper#Walk-Forward Design, Tuning, and Evaluation]]: reference for the QLIKE loss used as the secondary metric.
