---
aliases:
  - "Zhang, Li, and Zhang (2023)"
title: "A two-step framework for arbitrage-free prediction of the implied volatility surface"
authors:
  - "Wenyong Zhang"
  - "Lingfei Li"
  - "Gongqiu Zhang"
year: 2023
venue: "Quantitative Finance"
doi: "10.1080/14697688.2022.2135454"
status: cited
pdf: "[[lit_review/A two-step framework for arbitrage-free prediction of the implied volatility surface.pdf]]"
pdf_version: published
asset_class: "S&P 500 index options"
sample_period: "2009-2020"
forecast_object: "implied volatility surface, evaluated at the 374 observed points per day"
horizon: "1 day"
methods:
  - "LSTM prediction of surface features (sampled grid, PCA coefficients, VAE latent factors)"
  - "Feedforward network for surface construction with static no-arbitrage penalties"
benchmarks:
  - "DFW regression model of Dumas, Fleming and Whaley (1998) with previous-day coefficients"
  - "DFW interpolation in place of the network in step 2"
  - "PCA coefficients forecast by AR(1)"
evaluation_design: "single chronological split: training 1 January 2009 to 27 June 2018, test 28 June 2018 to 31 December 2020; no validation set"
loss_metrics:
  - "RMSE"
  - "MAPE"
headline_finding: "SAM-DNN and VAE-DNN have the lowest out-of-sample errors (test RMSE 0.0245 and 0.0248, against 0.0366 for DFW), and no calendar or butterfly violations are detected in their predicted surfaces."
tags:
  - literature
  - literature/forecasting
  - literature/no-arbitrage
---

# Zhang, Li, and Zhang (2023)

**A two-step framework for arbitrage-free prediction of the implied volatility surface.** Quantitative Finance 23(1): 21-34.

## Question
- How can the next-day implied volatility surface be predicted so that the predicted surface excludes static arbitrage?

## Data
- OptionMetrics implied volatility surfaces for S&P 500 index options, 1 January 2009 to 31 December 2020 (3021 days), 374 points per day, maturities from 10 to 730 calendar days.
- A fixed 154-point moneyness-maturity grid is filled with the DFW regression model.

## Method
- Step 1: an LSTM predicts surface features from the latest value and its weekly and monthly moving averages. Feature sets: the 154 sampled volatilities (SAM), three PCA coefficients, or VAE latent factors (dimension 10 retained).
- Step 2: a feedforward network maps predicted features, moneyness and maturity to implied volatility. Calendar, butterfly and large-moneyness conditions enter the loss as penalties on synthetic grids.

## Evaluation design
- About 9.5 years of training and 2.5 years of testing, including March 2020.
- Pairwise one-sided Diebold-Mariano tests on RMSE at the 1% level.

## Findings
- Test RMSE: SAM-DNN 0.0245, VAE-DNN 0.0248, SAM-DFW 0.0312, DFW 0.0366, PCA-DNN 0.0544, VAE-DFW 0.0647, PCA-DFW 0.0745.
- SAM-DNN and VAE-DNN are statistically indistinguishable and beat every other model.
- For each feature set, the network beats DFW interpolation in step 2.
- No violations are detected at observed points for the three network models; DFW shows calendar violations in particular.

## Limits and caveats
- Conditions are checked only on grids; the authors call the surface "almost free of static arbitrage".
- Dynamic arbitrage is not excluded.
- The only benchmark outside the framework is DFW with previous-day coefficients.

## Use in this study
- [[paper#Introduction]]: one of the recent machine-learning approaches (sequence model with constrained reconstruction) whose gains are empirical.
- [[paper#Literature Review]]: described as a two-step framework that predicts surface features (a sampled grid, principal components, or variational-autoencoder latent factors) and whose penalty-trained reconstruction network is almost free of static arbitrage.
- [[paper#Literature Review]]: example of Diebold-Mariano comparisons across surface models.
- [[paper#Models]]: supports describing a penalty-based network as arbitrage-aware.
- [[paper#Walk-Forward Design, Tuning, and Evaluation]]: precedent for pairwise Diebold-Mariano tests.
