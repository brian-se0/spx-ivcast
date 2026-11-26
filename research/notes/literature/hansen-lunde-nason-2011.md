---
aliases:
  - "Hansen, Lunde, and Nason (2011)"
title: "The Model Confidence Set"
authors:
  - "Peter R. Hansen"
  - "Asger Lunde"
  - "James M. Nason"
year: 2011
venue: "Econometrica"
doi: "10.3982/ECTA5771"
status: cited
pdf: "[[lit_review/Econometrica - 2011 - Hansen - The Model Confidence Set.pdf]]"
pdf_version: published
asset_class: "not applicable (applications: U.S. inflation forecasts and Taylor rule regressions)"
sample_period: "Inflation forecasts evaluated 1970:M1-1983:M12 and 1984:M1-1996:M9; Taylor rules 1979:Q1-2006:Q4"
forecast_object: "not a forecasting paper (procedure for selecting the set of best models under a user-specified loss)"
horizon: "not applicable"
methods:
  - "Model confidence set (sequential equivalence test with elimination rule)"
  - "T_max statistic with elimination rule e_max"
  - "T_R statistic with elimination rule e_R"
  - "Block bootstrap"
  - "MCS p-values"
benchmarks: []
evaluation_design: "Monte Carlo simulations of size and power; out-of-sample inflation forecasts with rolling-window estimation; in-sample Taylor rule regressions"
loss_metrics:
  - "User-specified loss"
  - "Mean square prediction error, reported as RMSE (inflation application)"
  - "KLIC, AIC and BIC with effective degrees of freedom (regression application)"
headline_finding: "A sequential test-and-eliminate procedure yields a set of models that contains the best model or models with a chosen confidence level and is larger when the data are less informative."
tags:
  - literature
  - literature/evaluation
---

# Hansen, Lunde, and Nason (2011)

**The Model Confidence Set.** Econometrica 79(2): 453-497.

## Question

- How can a set of models be built that contains the best model or models, in expected loss, with a given confidence and without naming a benchmark?

## Data

- Simulated losses, the Stock and Watson (1999) inflation forecasts, and 25 interest-rate regressions on U.S. data.

## Method

- With loss differentials d_ij,t = L_i,t - L_j,t, the null for a set M is that all mean differentials are zero. Start from all models, test at level alpha, remove one model on rejection and repeat; the survivors form the set.
- From t-statistics t_ij (pairwise) and t_i. (model against the average): T_max = max over i of t_i., with rule e_max = arg max t_i.; T_R = max over i, j of |t_ij|, with rule e_R = arg max over i of sup over j of t_ij. T_R is called a range statistic in the regression setting.
- Null distributions come from a block bootstrap, detailed in a separate supplement.
- A model's MCS p-value is the largest test p-value up to its elimination; the model is in the set if and only if that value is at least alpha.

## Evaluation design

- Simulations use block length 2, 1,000 resamples, n = 250 and alpha = 10%; the inflation application uses block length 12.

## Findings

- In simulations the best models are retained at a frequency almost always above 1 - alpha.
- The 1970-1983 inflation sample leaves relatively few models in the set; in 1984-1996 nearly all simple regression forecasts stay, except the month-over-month no-change forecast.

## Limits and caveats

- Loss differentials are assumed strictly stationary; the authors use rolling-window estimation because recursive estimation makes this implausible, and advise caution when forecasts rest on estimated parameters, notably for nested models.
- "Models remain in the MCS until proven inferior", so retained models need not be good.

## Use in this study

- [[paper#Literature Review]]: named as the comparison procedure that Shang and Kearney (2022) pair with an expanding-window design.
- [[paper#Walk-Forward Design, Tuning, and Evaluation]]: source of the model confidence set, with the T_R statistic and e_R elimination rule, used for statistical forecast comparison.
