---
aliases:
  - "Martini and Mingone (2021)"
title: "Explicit no arbitrage domain for sub-SVIs via reparametrization"
authors:
  - "Claude Martini"
  - "Arianna Mingone"
year: 2021
venue: "arXiv"
doi: "10.48550/arXiv.2106.02418"
status: cited
pdf: "[[lit_review/2106.02418v1.pdf]]"
pdf_version: preprint
asset_class: "not applicable"
sample_period: "not applicable"
forecast_object: "not a forecasting paper"
horizon: "not applicable"
methods:
  - "Reparametrization of the no-butterfly-arbitrage domain by the critical point of the function that bounds the SVI sigma parameter"
  - "Fukasawa necessary conditions"
  - "Numerical grid check of critical-point uniqueness for SSVI"
benchmarks:
  - "Gatheral-Jacquier sufficient conditions for SSVI"
evaluation_design: "not applicable"
loss_metrics: []
headline_finding: "Necessary-and-sufficient no-butterfly-arbitrage domains are fully explicit for the Vanishing, Extremal Decorrelated and Symmetric SVI sub-families and quasi-explicit for SSVI slices."
tags:
  - literature
  - literature/no-arbitrage
---

# Martini and Mingone (2021)

**Explicit no arbitrage domain for sub-SVIs via reparametrization.** arXiv preprint arXiv:2106.02418v1 [q-fin.MF].

## Question

- For which three-parameter SVI sub-families can the butterfly-arbitrage-free parameter set be written explicitly, without the numerical minimisations and root searches that general five-parameter SVI needs?

## Data

- None. No market data; the figures plot example smiles and domain boundaries at chosen parameter values.

## Method

- Works on one total-variance smile, starting from the authors' necessary-and-sufficient butterfly conditions for five-parameter SVI ([[martini-mingone-no-arbitrage-svi]]): Fukasawa's necessary conditions plus a lower bound on sigma.
- Families, three free parameters each: Vanishing Upward/Downward SVI (a = 0, rho = ±1), Extremal Decorrelated SVI (rho = 0, b = 2), Symmetric SVI (rho = m = 0), SSVI slices (theta, phi, rho).
- Reparametrization: the critical point of the function whose extremum gives the sigma bound becomes a parameter, and b (or the rescaled m) is recovered from the critical-point equation.

## Evaluation design

- Not applicable (theoretical). Critical-point uniqueness is proved for the Vanishing and Symmetric families (some Symmetric steps are checked on plots) and checked numerically on a 1000 × 1000 grid for SSVI.

## Findings

- Fully explicit necessary-and-sufficient domains for Vanishing Upward and Downward SVI (Propositions 3.2, 3.4), Extremal Decorrelated SVI (Proposition 4.2) and Symmetric SVI (Proposition 5.2).
- SSVI slices (Proposition 6.3): a necessary-and-sufficient parametrization that is quasi-explicit (one root of a one-dimensional function is computed numerically) and assumes the numerically supported uniqueness.
- Sufficient-only explicit sub-domains for Vanishing Upward SVI (Lemma 3.3) and SSVI (Lemma 6.6); the latter is weaker than the Gatheral-Jacquier sufficient condition while b(1+|rho|) stays low, and its sigma bound diverges as b(1+|rho|) approaches 2.
- The Long Term Heston SVI approximation is an SSVI slice, free of butterfly arbitrage once maturity exceeds an explicit threshold (Proposition 6.8).

## Limits and caveats

- Single-smile butterfly arbitrage only. Calendar-spread arbitrage across maturities is motivation and is not treated; SSVI is a slice here, not a surface.
- The authors call the interest "essentially of academic nature": three parameters may be too few to fit market data well.

## Use in this study

- [[paper#Literature Review]]: cited for making the no-butterfly-arbitrage domain explicit for several three-parameter SVI sub-families.
