# AI Exposure and Labor Market Outcomes
### Replication and Extension — Felten et al. (2021) × BLS OEWS 2025

An empirical analysis of how AI occupational exposure relates to wages
across the US labor market, with a focused case study on accounting
vs. software development.

> Inspired by Acemoglu & Restrepo (2018, 2019) task-based framework
> and Felten, Raj & Seamans (2021) AIOE index.

---

## The Puzzle

Two occupations with similar AI exposure scores face completely different
labor market trajectories. Why?

![Comparison](figures/assignment1_comparison.png)
*Despite similar AI exposure, software developers earn 60–80% more than
accountants and face growing employment while accounting contracts.*

---

## Research Questions

- Does AI exposure predict wages once education is controlled for?
- Does the wage-exposure gradient reflect sorting or protection?
- Why do accounting and software development diverge despite similar exposure?

---

## Data

| Source | File | Use |
|---|---|---|
| **Felten et al. (2021)** | `data/AIOE_DataAppendix.xlsx` | AI Occupational Exposure (AIOE) index |
| **BLS OEWS 2025** | `data/oews_2025/` | Median wages and employment (670 occupations) |
| **O*NET 29.0 (2023)** | `data/onet_education.xlsx` | Required education level per occupation |

---

## The Answer: Task Structure

The divergence comes from *where* AI exposure is concentrated within
each occupation — not the overall exposure level.

![Task Decomposition](figures/assignment1_task_decomposition.png)
*Accounting concentrates substitutable tasks at the core of the occupation;
software development maintains a deeper complementarity buffer.*

![Weighted Scores](figures/assignment1_weighted_scores.png)
*Accounting concentrates 60% of labor time in high-substitutability tasks
vs. 50% for software development.*

---

## Diverging Trajectories

![Trends](figures/assignment1_trends.png)
*Post-ChatGPT (Nov 2022): accounting employment contracts while software
development decelerates. Task structure predicts direction; exposure alone does not.*

---

## Regression Evidence

ln(w_i) = β₀ + β₁·AIOE_i + β₂·Education_i + ε_i

Estimated via WLS weighted by total employment.
N = 658 occupations (670 matched on AIOE × BLS; 658 with O*NET education data)

| Variable | Coefficient | Std. Error (HC3) | t | p-value |
|---|---|---|---|---|
| AIOE | 0.082** | 0.040 | 2.040 | 0.041 |
| Education Level | 0.114*** | 0.020 | 5.827 | <0.001 |
| Constant | 10.564*** | 0.094 | — | <0.001 |
| **R-squared** | **0.511** | | | |

\*\*\* p<0.001, \*\* p<0.05

![Regression](figures/assignment1_regression.png)
*The positive wage-exposure gradient reflects occupational sorting —
AI exposure concentrates in high-skill cognitive occupations already
well-paid before generative AI.*

---

## Key Finding

> AI exposure is **positively associated with wages** — a
> one-standard-deviation increase predicts roughly **8% higher pay**
> (β=0.082, HC3 p=0.041) — but this reflects **occupational sorting**,
> not protection. Task structure determines substitution vs.
> complementarity; exposure alone does not.

---

## Repository Structure

ai-labor-replication/
├── data/
│   ├── AIOE_DataAppendix.xlsx     ← Felten et al. exposure scores
│   ├── oews_2025/                 ← BLS OEWS 2025 wage & employment data
│   └── onet_education.xlsx        ← O*NET education requirements
├── notebooks/
│   ├── Assignment-analysis.ipynb  ← Main analysis pipeline
│   └── analysis.ipynb             ← Exploratory analysis
├── figures/
│   ├── assignment1_regression.png
│   └── regression_final_results.txt
├── requirements.txt
└── README.md

---

## Author

**[Arsham Nazeri](https://arsham-nazeri.github.io)**  
*Thinking about markets, institutions, technology, and the culture that shapes them.*
