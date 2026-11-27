---
aliases:
  - "Fengler, Härdle, and Mammen (2007)"
  - "Fengler, Hardle and Mammen (2007)"
title: "A Semiparametric Factor Model for Implied Volatility Surface Dynamics"
authors:
  - "Matthias R. Fengler"
  - "Wolfgang K. Härdle"
  - "Enno Mammen"
year: 2007
venue: "Journal of Financial Econometrics"
doi: "10.1093/jjfinec/nbm005"
status: cited
pdf: "[[lit_review/nbm005.pdf]]"
pdf_version: published
asset_class: "DAX index options (EUREX)"
sample_period: "January 1998 to May 2001"
forecast_object: "not a forecasting paper; models daily log implied volatility over moneyness and time to maturity"
horizon: "not applicable"
methods:
  - "semiparametric factor model with kernel-smoothed factor functions"
  - "augmented Dickey-Fuller tests on factor loadings"
  - "VAR(2) in levels on factor loadings"
benchmarks:
  - "Nadaraya-Watson estimator fitted to a single day"
evaluation_design: "in-sample; one full-sample estimation; no out-of-sample test"
loss_metrics:
  - "share of variance explained"
headline_finding: "Three factor functions explain up to 97% of the variation in DAX log implied volatilities, and their loadings are fitted with a VAR(2) in levels."
tags:
  - literature
  - literature/surface-dynamics
  - literature/surface-construction
---

# Fengler, Härdle, and Mammen (2007)

**A Semiparametric Factor Model for Implied Volatility Surface Dynamics.** Journal of Financial Econometrics 5(2): 189-218.

## Question
- How can the implied-volatility surface be reduced to a few factors when observations lie only on a few maturity strings that drift towards expiry, so that daily nonparametric fits need very large maturity bandwidths and become biased?

## Data
- Transaction-level DAX index options and futures from EUREX, January 1998 to May 2001; Black-Scholes implied volatilities use an index level backed out of futures prices.
- Implied volatilities outside 4%-80%, maturities under ten days and data beyond half a year to expiry are dropped; about 2.24 million observations remain, around 2,600 per day.

## Method
- Log implied volatility is modelled on moneyness (strike over futures price) and time to maturity as an invariant function plus L factor functions with daily loadings, estimated by iterated kernel-weighted least squares pooled over all days.
- Bandwidths of 0.04 (moneyness) and 0.06 years (maturity) keep adjacent expiries out of the same daily fit; a grid point is informed on the days a string passes near it.
- Factor functions are orthonormalised and ordered by loading variance, and a vector autoregression is fitted to the loadings.

## Evaluation design
- In-sample only: one full-sample estimation, judged by share of variance explained and by comparison with a single-day Nadaraya-Watson fit on 18 June 1998. No forecast, horizon or no-change benchmark appears.

## Findings
- One, two and three factor functions explain up to 89%, 94% and 97% of the variation; three are kept and read as level, moneyness slope and term-structure slope.
- ADF statistics are -2.67, -3.01 and -5.63 (critical values -2.87 at 5%, -3.44 at 1%); the authors report a unit root in the first two loadings at the 5% level, describe the statistics as not strongly significant, and model levels to avoid over-differencing.
- A VAR(2) is chosen; first own-lag coefficients are 0.958, 0.902 and 0.795, adjusted R-squared 0.958, 0.956 and 0.797.
- The fit is smoother than Nadaraya-Watson despite smaller bandwidths, and extrapolates a smile where a day has almost no observations.

## Limits and caveats
- The VAR uses estimated loadings; its validity under kernel smoothing is a conjecture.
- Factor functions use the entire sample, and the authors call the single-date comparison unbalanced.
- VAR residuals are heteroskedastic.

## Use in this study

- [[paper#Literature Review]]: cited as an in-sample precedent for low-dimensional surface structure: three factor functions account for 97% of the variation in DAX log implied volatility, with loadings modeled by a vector autoregression in levels.
- [[paper#Literature Review]]: cited for the point that exchange-traded implied volatilities are observed only along a few maturity strings, so a daily nonparametric fit needs a wide maturity bandwidth that biases the estimated surface.
