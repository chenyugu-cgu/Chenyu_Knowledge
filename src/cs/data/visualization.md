# Visualization

Visualization is how we see patterns, communicate findings, and catch mistakes. A good plot reveals what tables hide; a bad plot misleads. It serves two distinct goals: **exploration** (for yourself) and **explanation** (for an audience).

## Choosing the Right Chart

| Goal | Chart |
|---|---|
| Distribution of one variable | histogram, density, box/violin |
| Relationship between two | scatter plot |
| Trend over time | line chart |
| Comparison across categories | bar chart |
| Part-to-whole | stacked bar (avoid pie for many slices) |
| Correlation matrix | heatmap |
| High-dimensional structure | PCA / t-SNE / UMAP projection |

Match the chart to the data type and the question — not to what looks impressive.

## Anscombe's Quartet

Four datasets with **identical** means, variances, correlation, and regression line look completely different when plotted — some linear, some curved, some driven by an outlier. The lesson: **always plot the data** before trusting summary statistics.

## Principles of Honest Graphics

- **Maximize the data-ink ratio** (Tufte): remove chartjunk, gridlines, 3-D effects.
- **Start bar charts at zero** — truncated axes exaggerate differences.
- **Label directly** and keep a clear title, axis labels, and units.
- **Use color purposefully** and choose colorblind-safe, perceptually uniform palettes (e.g. viridis).
- **Show uncertainty** — error bars, confidence bands, or individual points.

## Exploratory vs. Explanatory

- **Exploratory:** fast, many plots, defaults are fine — you are looking for surprises.
- **Explanatory:** polished, focused on a single message, annotated for the reader.

## Example: A Quick EDA Panel

```python
import seaborn as sns
import matplotlib.pyplot as plt

df = sns.load_dataset("penguins").dropna()

fig, ax = plt.subplots(1, 2, figsize=(11, 4))
sns.scatterplot(data=df, x="bill_length_mm", y="body_mass_g",
                hue="species", ax=ax[0])
sns.boxplot(data=df, x="species", y="flipper_length_mm", ax=ax[1])
fig.suptitle("Penguin morphology by species")
plt.tight_layout()
plt.show()
```

## See Also

- [Data Cleaning](cleaning.md)
- [Statistical Modeling](modeling.md)
- [Distributions](../../math/probability/distributions.md)
