# Data Cleaning

Real data is messy — missing values, duplicates, inconsistent formats, outliers, and errors. Cleaning ("data wrangling") is unglamorous but decisive: models inherit the flaws of their data.

## Tidy Data

Aim for **tidy** structure: each variable is a column, each observation a row, each type of observational unit a table. Most analysis tools assume this shape, and reshaping (pivot/melt) is the first step toward it.

## Missing Data

Diagnose the mechanism before acting:
- **MCAR** (missing completely at random) — safe to drop or impute simply.
- **MAR** (missing at random, given observed data) — model-based imputation works.
- **MNAR** (missing not at random) — missingness depends on the unseen value; needs care and often domain knowledge.

Strategies: drop rows/columns (if sparse), impute (mean/median/mode, k-NN, regression, MICE), or add a **missingness indicator**. Always impute using training-set statistics only (no leakage).

## Outliers

Detect with the IQR rule (\\(x < Q_1 - 1.5\,\text{IQR}\\) or \\(x > Q_3 + 1.5\,\text{IQR}\\)), z-scores, or robust methods. Decide deliberately: outliers may be errors (fix/remove) **or** the most important signal (fraud, faults) — never delete blindly.

## Common Cleaning Tasks

- **Duplicates:** detect and drop exact or fuzzy duplicates.
- **Type consistency:** parse dates, numbers, booleans; standardize units.
- **Categorical tidying:** unify casing/spelling ("USA"/"U.S.A."/"us").
- **Range/validity checks:** ages ≥ 0, percentages in [0,100], valid foreign keys.
- **Text normalization:** trim whitespace, fix encodings.

## Example: pandas Cleaning Pipeline

```python
import pandas as pd
import numpy as np

df = pd.read_csv("data.csv")

df = df.drop_duplicates()
df["date"] = pd.to_datetime(df["date"], errors="coerce")
df["category"] = df["category"].str.strip().str.lower()

# Median-impute a numeric column; flag what was missing
df["income_missing"] = df["income"].isna().astype(int)
df["income"] = df["income"].fillna(df["income"].median())

# IQR-based outlier clipping
q1, q3 = df["income"].quantile([0.25, 0.75])
iqr = q3 - q1
df["income"] = df["income"].clip(q1 - 1.5*iqr, q3 + 1.5*iqr)
```

## Document Everything

Record every transformation. A reproducible cleaning script (not manual spreadsheet edits) is the difference between trustworthy and unverifiable analysis.

## See Also

- [Feature Engineering](../ml/features.md)
- [Visualization](visualization.md) — spot problems by plotting first.
