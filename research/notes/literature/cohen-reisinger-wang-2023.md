---
aliases:
  - "Cohen, Reisinger and Wang (2023)"
title: "Arbitrage-Free Neural-SDE Market Models"
authors:
  - "Samuel N. Cohen"
  - "Christoph Reisinger"
  - "Sheng Wang"
year: 2023
venue: "Applied Mathematical Finance"
doi: "10.1080/1350486X.2023.2257217"
status: uncited
pdf: "[[lit_review/Arbitrage-Free Neural-SDE Market Models.pdf]]"
pdf_version: published
asset_class: "European options on a stock (simulated data)"
sample_period: "simulated data from a Heston stochastic local volatility model"
forecast_object: "joint dynamics of stock and option prices (drift and diffusion of an SDE system)"
horizon: "not stated"
methods:
  - "neural SDE with constrained neural networks"
  - "state space free of static arbitrage"
benchmarks: []
evaluation_design: "numerical experiments against a known ground-truth model"
loss_metrics: []
headline_finding: "A neural SDE for the option book can be calibrated so that linear no-arbitrage inequalities are guaranteed."
tags:
  - literature
  - literature/surface-dynamics
  - literature/no-arbitrage
---

# Cohen, Reisinger and Wang (2023)

**Arbitrage-Free Neural-SDE Market Models.** Applied Mathematical Finance 30(1): 1-46.

## Question
- How can the joint dynamics of liquid vanilla options be modelled without static arbitrage?

## Data
- Simulated Heston stochastic local volatility data; market data are left to future work.

## Method
- Neural networks for drift and diffusion with constraints that preserve no-arbitrage.

## Evaluation design
- Comparison with a known ground truth in an idealized setting.

## Findings
- Calibrated models satisfy the set of linear inequalities by construction.

## Limits and caveats
- No market data in this paper.

## Use in this study
Relates to no-arbitrage modelling of option-surface dynamics, a continuous-time alternative to the statistical next-session forecasts studied here.
