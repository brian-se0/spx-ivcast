---
aliases:
  - "Fengler (2009)"
title: "Arbitrage-free smoothing of the implied volatility surface"
authors:
  - "Matthias R. Fengler"
year: 2009
venue: "Quantitative Finance"
doi: "10.1080/14697680802595585"
status: cited
pdf: "[[lit_review/Arbitrage-free smoothing of the implied volatility surface.pdf]]"
pdf_version: published
asset_class: "DAX index options (EUREX settlement data)"
sample_period: "single day, 13 June 2000"
forecast_object: "not a forecasting paper"
horizon: "not applicable"
methods:
  - "Natural cubic spline smoothing of call prices under linear no-arbitrage constraints (convex quadratic program)"
  - "Thin plate spline initial estimate on a forward-moneyness grid"
benchmarks:
  - "Heston (1993) model"
evaluation_design: "single-day demonstration plus a resampling simulation with 100 perturbed samples per expiry"
loss_metrics:
  - "RMSE of prices"
  - "RMSE of implied volatilities"
headline_finding: "A natural cubic spline fitted to call prices under linear shape constraints, applied from the last expiry to the first, yields an implied volatility surface without strike or calendar arbitrage even when the input quotes contain arbitrage."
tags:
  - literature
  - literature/no-arbitrage
  - literature/surface-construction
---

# Fengler (2009)

**Arbitrage-free smoothing of the implied volatility surface.** Quantitative Finance 9(4): 417-428.

## Question
- How can an implied volatility surface be smoothed so that it is arbitrage-free when the observed quotes are not, giving local volatility pricers a usable input?

## Data
- DAX option settlement data (EUREX), 13 June 2000: eight expiries from 3 to 398 calendar days; spot 7268.91.
- The 3-day expiry is deleted when the whole surface is estimated.

## Method
- Per expiry, a natural cubic spline is fitted to call prices by penalized least squares, written as a convex quadratic program.
- Linear inequality constraints impose convexity, monotonicity in strike and price bounds.
- For the surface, a thin plate spline pre-estimate is placed on a forward-moneyness grid and the program is solved from the last expiry to the first, with added constraints reflecting that total variance is non-decreasing in maturity at fixed forward-moneyness.

## Evaluation design
- Single-day illustration: residuals at 68 and 398 days and a down-and-out put delta from a local volatility pricer.
- Simulation against Heston: smiles perturbed by normal errors (standard deviation 10 to 50 basis points), 100 simulations, single expiries.

## Findings
- Input data need not be arbitrage-free, and the program has a unique minimizer.
- Removing arbitrage moves implied volatilities by around 10 basis points at 68 days and around 30 at 398 days.
- Local discontinuities in the barrier-option delta vanish with the smoothed surface.
- Spline RMSE is below Heston's in almost every case; Heston is superior only on data generated from Heston.

## Limits and caveats
- Calendar arbitrage is excluded at the knots; between knots it cannot be ruled out, though the author considers it very unlikely.
- One trading day of data.

## Use in this study
- [[paper#Literature Review]]: cited as an early treatment of recovering a smooth surface from raw quotes as a modelling problem in its own right, through arbitrage-free smoothing splines.
