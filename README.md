# AI Exposure and Labor Market Outcomes
## Replication and Extension — Felten et al. (2021) × BLS OEWS 2025

An empirical analysis of how AI occupational exposure relates to wages 
across the US labor market, with a focused case study on accounting 
vs. software development.

Inspired by Acemoglu & Restrepo (2018, 2019) task-based framework 
and Felten, Raj & Seamans (2021) AIOE index.

---

## Research Questions

- Does AI exposure predict wages once education is controlled for?
- Does the wage-exposure gradient reflect sorting or protection?
- Why do accounting and software development diverge despite similar exposure?

---

## Data Sources

| Source | File | Use |
|---|---|---|
| **Felten et al. (2021)** | `data/AIOE_DataAppendix.xlsx` | AI exposure scores |
| **BLS OEWS 2025** | `data/oews_2025/` | Wages and employment |
| **O*NET 29.0 (2023)** | `data/onet_education.xlsx` | Education requirements |

---

## Methods

- Merged AIOE index with BLS OEWS 2025 on 6-digit SOC code
- O*NET education level as independent skill proxy
- WLS regression weighted by total employment
- HC3 heteroskedasticity-robust standard errors
- Education collapsed to modal category per SOC code

---

## Final Regression Specification

ln(w_i) = β₀ + β₁·AIOE_i + β₂·Education_i + ε_i

N=658 occupations (670 matched on AIOE × BLS, 658 with O*NET education data)

---

## Key Results (HC3 Robust SEs)

| Variable | Coefficient | Std. Error | t | p-value |
|---|---|---|---|---|
| AIOE | 0.082** | 0.040 | 2.040 | 0.041 |
| Education Level | 0.114*** | 0.020 | 5.827 | <0.001 |
| Constant | 10.564*** | 0.094 | — | <0.001 |
| R-squared | 0.511 | | | |

**Interpretation:** The positive wage-exposure gradient reflects 
occupational sorting — AI exposure concentrates in high-skill 
cognitive occupations already well-paid before generative AI. 
Whether exposure becomes substitution or complementarity is 
determined by task structure, not exposure level.

---

## Notebooks

| Notebook | Contents |
|---|---|
| `notebooks/Assignment-analysis.ipynb` | Full analysis pipeline |
| `notebooks/analysis.ipynb` | Exploratory analysis |

---

## Outputs

| File | Description |
|---|---|
| `outputs/assignment1_regression.png` | Main regression figure |
| `outputs/regression_final_results.txt` | HC3 regression output |

---

## Repository Structure


ai-labor-replication/
data/
AIOE_DataAppendix.xlsx    ← Felten et al. exposure scores
oews_2025/                ← BLS OEWS 2025 data
onet_education.xlsx       ← O*NET education requirements
notebooks/
Assignment-analysis.ipynb ← Main analysis
outputs/
assignment1_regression.png
regression_final_results.txt
requirements.txt
README.md

---

## Author

[Arsham Nazeri](https://arsham-nazeri.github.io) · ·
