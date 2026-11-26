---
aliases:
  - "Cont and da Fonseca (2002)"
title: "Dynamics of implied volatility surfaces"
authors:
  - "Rama Cont"
  - "José da Fonseca"
year: 2002
venue: "Quantitative Finance"
doi: "10.1088/1469-7688/2/1/304"
status: cited
pdf: "[[lit_review/Dynamics of implied volatility surfaces.pdf]]"
pdf_version: published
asset_class: "S&P 500 and FTSE 100 index options"
sample_period: "S&P 500: 2 March 2000 to 2 February 2001; FTSE 100: more than 2 years, exact span not clearly stated"
forecast_object: "not a forecasting paper"
horizon: "not applicable"
methods:
  - "Nadaraya-Watson kernel smoothing of daily surfaces"
  - "Karhunen-Loeve decomposition of daily log implied-volatility changes"
  - "AR(1)/Ornstein-Uhlenbeck factor model"
benchmarks: []
evaluation_design: "not applicable"
loss_metrics: []
headline_finding: "Daily deformations of index-option surfaces are driven by a small number of orthogonal, interpretable, persistent factors."
tags:
  - literature
  - literature/surface-dynamics
---

# Cont and da Fonseca (2002)

**Dynamics of implied volatility surfaces.** Quantitative Finance 2(1): 45-60.

## Question
- How does the whole surface, across moneyness and maturity jointly, deform from day to day?

## Data
- End-of-day European calls and puts on the S&P 500 (CBOE) and FTSE 100 (LIFFE); out-of-the-money options, moneyness within [0.5, 1.5], maturities of about a month to a year.

## Method
- Kernel-smooths each day's quotes into a surface, then decomposes daily log implied-volatility changes into eigenmodes and studies the projection on each.

## Evaluation design
- Descriptive and in-sample; no forecasting exercise.

## Findings
- The first three eigenmodes account for 98% of variance (S&P 500) and more than 95% (FTSE): level, opposite moves in out-of-the-money calls and puts, and curvature.
- The S&P 500 level share is around 80% in the text and 94% in Table 1; FTSE 96%.
- Projections are highly autocorrelated and mean-reverting, close to AR(1): level coefficient 0.965 (S&P 500), 0.9808 (FTSE).
- Level moves correlate negatively with index returns (-0.66, S&P 500); shape moves hardly at all.

## Limits and caveats
- About one year of S&P 500 data; second-order statistics only.
- The factor model is proposed, not tested for predictive accuracy.

## Use in this study
- [[paper#Introduction]]: valuation, hedging and risk depend on joint moneyness-maturity dynamics.
- [[paper#Introduction]]: a few factors capture a large share of surface dynamics.
- [[paper#Literature Review]]: deformations represented by a few interpretable factors with risk-management meaning.
- [[paper#Literature Review]]: a few orthogonal factors explain much of the daily deformation of index-option surfaces.
- [[paper#Feature Engineering and Targets]]: persistence and low-dimensional structure behind the feature design.
