# Construction Scope 3 Cost Forecasting

## Forecasting Carbon-Driven Cost Pressures for UK Subcontractors

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Data](https://img.shields.io/badge/Data-ONS%20%2F%20UK%20ETS-orange)
![Methods](https://img.shields.io/badge/Methods-SARIMA%20%7C%20ETS%20%7C%20Monte%20Carlo-purple)
![License](https://img.shields.io/badge/License-MIT-green)

---

## The Business Question

> *"How will Scope 3 emissions-related cost pressures evolve for UK construction subcontractors over the next 12-24 months, and which material categories will drive the greatest financial exposure?"*

UK construction firms are facing mandatory Scope 3 reporting requirements under RICS PS3 and increasing pressure from Tier 1 contractors to quantify and reduce embodied carbon. This project forecasts the financial cost implications using construction material price indices and UK ETS carbon pricing data, so subcontractors can plan procurement, pricing, and decarbonisation strategy.

---

## Business Context

Scope 3 Category 1 (purchased goods and services) typically accounts for 70-80% of total construction Scope 3 emissions. Three forces are driving cost escalation:

| Driver | Mechanism |
|--------|-----------|
| Carbon pricing | UK ETS price trajectory and potential CBAM extension |
| Low-carbon material premiums | Green steel, GGBS, mass timber command price premiums |
| Supply chain transparency costs | Carbon data collection, verification, reporting |

---

## Data

The analysis uses **calibrated synthetic data** that reproduces the statistical properties of published ONS PPI construction material series (steel EW6T, concrete JUW4, timber JUW6) and UK ETS auction clearing prices. Seasonal patterns, trend direction, post-COVID price spikes, and ETS price trajectory are all calibrated to published government figures.

The ONS PPI MM22 dataset was partially discontinued in 2020; the methodology is designed to be transferable to live ONS data feeds as series are migrated to the PPI time series endpoint.

---

## Methods

| Model | Use Case | Key Parameter |
|-------|----------|--------------|
| SARIMA(1,1,1)(1,1,1)12 | Steel PPI 12-month forecast | Seasonal pattern = annual |
| ETS(A,A,A) | Timber and concrete price trends | Holt-Winters additive |
| OLS regression | ETS price trend + policy dummy | HAC standard errors |
| Monte Carlo (10,000 sims) | Aggregate subcontractor exposure | Correlated material/carbon inputs |

---

## Key Findings

All metrics are computed from the calibrated data and reported in the notebook. The analysis produces:

- 12-month steel PPI forecast with 90% confidence intervals
- UK ETS carbon price projection with policy break regression
- Monte Carlo distribution of total Scope 3 cost exposure (P10/P50/P90)
- GGBS substitution break-even analysis
- Executive summary dashboard with scenario comparison

---

## Repository Structure

```
construction-scope3-cost-forecasting/
|-- notebook/
|   +-- scope3_cost_forecasting.ipynb
+-- README.md
```

---

## Skills Demonstrated

`Python` `Pandas` `Statsmodels` `SARIMA` `ETS` `Time Series Forecasting` `ONS Data` `Carbon Economics` `Monte Carlo Simulation` `Matplotlib` `Seaborn` `UK ETS` `Scope 3`

---

## Author

**Yenlik Gaisina** -- Data & Sustainability Analyst | Cambridge Data Science & AI

[LinkedIn](https://www.linkedin.com/in/yenlik-gaisina/) | [Portfolio](https://gaisina.co.uk/portfolio.html)
