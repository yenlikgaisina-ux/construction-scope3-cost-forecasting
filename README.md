# 📈 Construction Scope 3 Cost Forecasting

## Forecasting Carbon-Driven Cost Pressures for UK Subcontractors

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Data](https://img.shields.io/badge/Data-ONS%20%2F%20HMRC-orange)
![Methods](https://img.shields.io/badge/Methods-ARIMA%20%7C%20ETS%20%7C%20Seasonal%20Decomposition-purple)
![License](https://img.shields.io/badge/License-MIT-green)

---

## The Business Question

> *"How will Scope 3 emissions-related cost pressures evolve for UK construction subcontractors over the next 12-24 months, and which material categories will drive the greatest financial exposure?"*

UK construction firms are facing mandatory Scope 3 reporting requirements under RICS PS3 (April 2024) and increasing pressure from Tier 1 contractors to quantify and reduce embodied carbon. This project forecasts the financial cost implications -- using published ONS price indices and HMRC trade data -- so subcontractors can plan procurement, pricing, and decarbonisation strategy.

---

## Business Context

Scope 3 Category 1 (purchased goods and services) typically accounts for **70-80% of total construction Scope 3 emissions**. For a UK subcontractor with £50M annual turnover, this translates to approximately **10,000-14,000 tCO2e per year**, with an implied carbon cost of **£600k-£1.4M** under current UK ETS carbon price trajectories.

Three forces are driving cost escalation:

| Driver | Mechanism | Estimated Impact |
|--------|-----------|-----------------|
| Carbon pricing | UK ETS price rise from ~£45/t to projected £80-120/t by 2030 | +£350k-£750k for typical subcontractor |
| Low-carbon material premiums | Green steel, GGBS, mass timber command 10-35% price premium | +£180k-£420k per £50M turnover |
| Supply chain transparency costs | Carbon data collection, verification, reporting | +£40k-£80k per year |

---

## Methods

### Data Sources
- **ONS Producer Price Index (PPI)**: Monthly construction material price series (Jan 2018-Dec 2024)
- **HMRC Overseas Trade Statistics**: Import volumes for steel, concrete, aluminium, timber
- **UK ETS auction results**: Carbon price history (2021-2024)
- **BEIS/Desnz conversion factors**: Emission factors for material categories

### Models Applied
| Model | Use Case | Key Parameter |
|-------|----------|--------------|
| SARIMA(1,1,1)(1,1,1)12 | Steel PPI 12-month forecast | Seasonal pattern = annual |
| ETS(A,A,A) | Timber and concrete price trends | Holt-Winters additive |
| Carbon price regression | ETS price ~ policy signal | OLS with AR(1) residuals |
| Portfolio cost model | Aggregate subcontractor exposure | Monte Carlo (1,000 sims) |

---

## Key Findings

| Metric | Value |
|--------|-------|
| Steel embodied carbon cost (current) | £38/t material |
| Projected steel cost uplift by Dec 2025 | +£12-18/t (+31-47%) |
| GGBS premium over standard CEM I | 8-14% (narrowing) |
| Median 12-month Scope 3 cost increase | +£127k per £50M turnover |
| 90th percentile scenario (ETS spike) | +£312k per £50M turnover |
| Break-even point for GGBS substitution | Month 7 of project cycle |

---

## Repository Structure

```
construction-scope3-cost-forecasting/
├── notebook/
│   └── scope3_cost_forecasting.ipynb   # Full analysis with executed outputs
├── .gitignore
└── README.md
```

---

## Skills Demonstrated

`Python` `Pandas` `Statsmodels` `ARIMA` `Time Series Forecasting` `ONS Data` `HMRC Trade Data` `Carbon Economics` `Monte Carlo Simulation` `Matplotlib` `Seaborn` `UK ETS` `Scope 3`

---

## Author

**Yenlik Gaisina** -- Data & Sustainability Analyst | Cambridge Data Science & AI
[LinkedIn](https://www.linkedin.com/in/yenlik-gaisina) | [Portfolio](https://gaisina.co.uk/portfolio)
