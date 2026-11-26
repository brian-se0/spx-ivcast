---
aliases:
  - "Bali, Beckmeyer, Mörke and Weigert (2023)"
title: "Option Return Predictability with Machine Learning and Big Data"
authors:
  - "Turan G. Bali"
  - "Heiner Beckmeyer"
  - "Mathis Mörke"
  - "Florian Weigert"
year: 2023
venue: "The Review of Financial Studies"
doi: "10.1093/rfs/hhad017"
status: uncited
pdf: "[[lit_review/hhad017.pdf]]"
pdf_version: published
asset_class: "equity options"
sample_period: "1996-2020 (more than 12 million observations)"
forecast_object: "future option returns"
horizon: "not stated"
methods:
  - "ridge, lasso and elastic net"
  - "gradient-boosted regression trees"
  - "random forests"
  - "feed-forward neural networks"
benchmarks:
  - "linear models"
evaluation_design: "out-of-sample testing period"
loss_metrics:
  - "out-of-sample R2"
headline_finding: "Allowing nonlinearities significantly raises out-of-sample predictive performance for option returns, with profitable long-short portfolios after costs."
tags:
  - literature
  - literature/machine-learning
  - literature/option-returns
---

# Bali, Beckmeyer, Mörke and Weigert (2023)

**Option Return Predictability with Machine Learning and Big Data.** The Review of Financial Studies 36(9): 3548-3602.

## Question
- Do nonlinear machine learning models improve prediction of option returns?

## Data
- Option and stock characteristics, 1996-2020.

## Method
- Penalized regressions, tree models and neural networks, plus equal-weighted ensembles.

## Evaluation design
- Out-of-sample R2 following Gu, Kelly and Xiu (2020).

## Findings
- No linear model has positive out-of-sample R2 over the whole test sample; all nonlinear models do, best being gradient-boosted trees (2.26%); confirmed with Diebold-Mariano tests.

## Limits and caveats
- Targets option returns, not implied volatility.

## Use in this study
Relates as a comparable machine-learning horse race (penalized regressions, forests, boosting, neural networks) in option markets, for a different target.
