---
aliases:
  - "Huang and Lawryshyn (2025)"
title: "Deep Hedging Under Market Frictions: A Comparison of DRL Models for Options Hedging with Impact and Transaction Costs"
authors:
  - "Eric Huang"
  - "Yuri Lawryshyn"
year: 2025
venue: "Journal of Risk and Financial Management"
doi: "10.3390/jrfm18090497"
status: uncited
pdf: "[[lit_review/jrfm-18-00497-v2.pdf]]"
pdf_version: published
asset_class: "simulated underlying and option (European options)"
sample_period: "not applicable"
forecast_object: "not a forecasting paper (hedging policy learned by reinforcement learning)"
horizon: "not stated"
methods:
  - "DDPG"
  - "TD3"
  - "SAC"
benchmarks:
  - "delta hedging"
evaluation_design: "simulated price paths"
loss_metrics:
  - "expected hedging loss"
  - "5th percentile CVaR"
headline_finding: "TD3 and SAC agents outperform delta hedging under market impact, slippage and transaction costs, cutting expected hedging losses by about two thirds."
tags:
  - literature
  - literature/hedging
---

# Huang and Lawryshyn (2025)

**Deep Hedging Under Market Frictions: A Comparison of DRL Models for Options Hedging with Impact and Transaction Costs.** J. Risk Financial Manag. 18(9): 497.

## Question
- Can reinforcement-learning agents learn hedging strategies when permanent market impact, execution slippage and transaction costs are present?

## Data
- Simulated price paths; no market data.

## Method
- Three RL models (DDPG, TD3, SAC) are compared in friction-intensive hedging environments.

## Evaluation design
- Comparison against delta hedging across simulated paths and friction settings.

## Findings
- TD3 and SAC cut expected hedging losses by over two thirds; per the conclusion SAC reaches about a 50% reduction in CVaR (TD3 about 20%).

## Limits and caveats
- Results are simulation-based.

## Use in this study
Not directly related.
