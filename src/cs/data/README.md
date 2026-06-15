# Data Science Practices

Data science turns raw data into understanding and decisions. It blends statistics, programming, and domain knowledge into a repeatable workflow. Where [machine learning](../ml/README.md) supplies the algorithms, data science supplies the **process** around them.

## The Workflow

1. **Frame the question** — what decision will this inform?
2. **Acquire data** — databases, APIs, files, sensors.
3. **Clean and prepare** — fix errors, handle missing values, reshape. See [Data Cleaning](cleaning.md).
4. **Explore (EDA)** — summary statistics and [visualization](visualization.md) to form hypotheses.
5. **Model** — statistics or ML to quantify relationships and predict. See [Statistical Modeling](modeling.md).
6. **Validate** — test against held-out data; check assumptions.
7. **Communicate** — translate findings into clear narratives and visuals.
8. **Deploy and monitor** — put models into production and watch for drift.

Most of the effort (often 60–80%) lives in steps 3–4: getting the data right.

## Tools of the Trade

- **Python:** pandas, NumPy, scikit-learn, matplotlib/seaborn, statsmodels.
- **R:** tidyverse, ggplot2 — strong for statistics.
- **SQL:** the lingua franca of data retrieval.
- **Notebooks:** Jupyter for exploration and reproducible reporting.

## Principles

- **Reproducibility** — version control, pipelines, fixed seeds.
- **Skepticism** — correlation ≠ causation; question every surprising result.
- **Leakage awareness** — never let the future or the target contaminate features.
- **Honesty about uncertainty** — report intervals, not just point estimates.

## Chapter Map

- [Data Cleaning](cleaning.md)
- [Visualization](visualization.md)
- [Statistical Modeling](modeling.md)

This section rests on [Probability and Statistics](../../math/probability/README.md).
