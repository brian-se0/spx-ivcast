---
aliases:
  - "Chalamandaris and Tsekrekos (2010)"
title: "Predictable dynamics in implied volatility surfaces from OTC currency options"
authors:
  - "Georgios Chalamandaris"
  - "Andrianos E. Tsekrekos"
year: 2010
venue: "Journal of Banking & Finance"
doi: "10.1016/j.jbankfin.2009.11.014"
status: cited
pdf: "[[lit_review/1-s2.0-S0378426609003112-main.pdf]]"
pdf_version: published
asset_class: "OTC currency options on 25 exchange rates against the euro"
sample_period: "1 January 1999 to 21 May 2007 for the ten most liquid rates; later starts for the rest"
forecast_object: "implied-volatility surface through three static factors"
horizon: "1-5 days"
methods:
  - "static factor model by asymptotic principal components, three factors"
  - "VAR on the factors, lags by BIC"
benchmarks:
  - "random walk for the factors"
evaluation_design: "recursive out-of-sample forecasts after an initial 100 daily surfaces; Diebold-Mariano tests by surface segment; simulated one-day delta-neutral straddle trading"
loss_metrics:
  - "MSE of implied volatilities"
  - "R2 of actual on predicted implied volatilities"
  - "mean correct prediction of direction of change"
  - "trading profit"
headline_finding: "VARs on three static factors forecast the systematic part of FX surfaces better than a factor random walk up to three days ahead, in many but not all segments, and trading profits shrink or vanish with transaction costs."
tags:
  - literature
  - literature/forecasting
  - literature/surface-dynamics
---

# Chalamandaris and Tsekrekos (2010)

**Predictable dynamics in implied volatility surfaces from OTC currency options.** Journal of Banking & Finance 34: 1175-1188.

## Question
- Can the latent factors behind surface dynamics deliver out-of-sample surface forecasts with economic value?

## Data
- Daily dealer-quoted implied volatilities at 14 expiries (1 week to 10 years) and five deltas per currency.

## Method
- Three principal-component factors per surface (level, term structure, jump-fear), forecast with a VAR.

## Evaluation design
- Forecasts 1 to 5 days ahead against the factor random walk.
- Three straddle trading rules, 1000 euros a day, with and without costs of 20 volatility basis points.

## Findings
- Three factors explain 91% of surface variance on average; factors are persistent.
- One day ahead, VAR average MSE is below the random walk's for all 25 currencies; the edge holds at 3 days and is gone at 5.
- Significance holds in many, not all, segments; whole-surface superiority is hard to establish.
- After costs, the one-straddle rules stay profitable on average and the two-straddle rule turns negative.

## Limits and caveats
- Bid-ask spreads are ignored; three factors are fixed ad hoc; no no-arbitrage restrictions.

## Use in this study
- [[paper#Introduction]]: motivation for forecasting the whole surface.
- [[paper#Introduction]]: a few factors capture much of surface dynamics.
- [[paper#Literature Review]]: option prices embed volatility information for pricing, hedging and portfolio management.
- [[paper#Literature Review]]: static factors and VARs improve short-horizon forecasts of the systematic component, unevenly across regions.
- [[paper#Literature Review]]: delta-hedged trading evaluation; gains need not survive frictions.
- [[paper#Feature Engineering and Targets]]: persistent, low-dimensional structure behind the feature design.
