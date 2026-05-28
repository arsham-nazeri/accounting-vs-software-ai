# Credential Without Protection
## AI Exposure and Diverging Labor Market Outcomes in Accounting vs. Software Development

An empirical analysis of why two occupations with similar AI exposure 
scores — accountants and software developers — face fundamentally 
different labor market trajectories.

---

## Key Finding

> AI exposure scores alone do not predict labor market outcomes. 
> What matters is *where within an occupation* that exposure is 
> concentrated, and whether substitutable tasks are central or 
> peripheral to the occupation's core value proposition.

---

## Data Sources
- **Felten, Raj & Seamans (2021)** — AI Occupational Exposure (AIOE) index
- **BLS Occupational Employment & Wage Statistics (OEWS) 2025**
- **Fedyk et al. (2022)** — Resume-based accounting displacement estimates
- **Peng et al. (2023)** — GitHub Copilot RCT

## Methods
- Task decomposition using O*NET and Barragán Moreno et al. (2025)
- Weighted Task Substitutability Score (labor-share weighted)
- OLS and WLS regression across 670 occupations (122M workers)
- Indexed employment and wage trajectories (2019–2025)

## Results

| | Accountants & Auditors | Software Developers |
|---|---|---|
| AIOE Score | 1.48 | 1.20 |
| Median Wage | $83,680 | $135,980 |
| Labor time at risk | 60% | 50% |
| Post-2022 trend | ↓ Declining | ↑ Growing |

WLS regression: being in a high-wage, high-exposure occupation 
predicts a **67% wage premium** (p<0.001), but AI exposure alone 
is not significant — consistent with Jaccoud (2025).

## Visualizations

### AI Exposure, Wages & Employment
![Comparison](figures/assignment1_comparison.png)

### Task-Level AI Substitutability
![Task Decomposition](figures/assignment1_task_decomposition.png)

### Weighted Task Substitutability
![Weighted Scores](figures/assignment1_weighted_scores.png)

### Diverging Labor Market Trajectories
![Trends](figures/assignment1_trends.png)

### Regression Analysis
![Regression](figures/assignment1_regression.png)

## Paper
Full paper available as `main.tex` (compile with pdflatex + bibtex).

## Author
[Arsham Nazeri](https://arsham-nazeri.github.io) ·
Thinking about markets, institutions, technology, and the culture 
that shapes them.