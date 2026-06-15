# Statistical Modeling

Statistical modeling describes relationships in data with mathematical structure, quantifies uncertainty, and supports inference and prediction. Where machine learning often prioritizes prediction, statistical modeling emphasizes **interpretation** and **inference**.

## Linear Regression

The workhorse model relates a response to predictors linearly:
\\[
y = \beta_0 + \beta_1 x_1 + \cdots + \beta_p x_p + \varepsilon, \qquad \varepsilon \sim \mathcal{N}(0, \sigma^2).
\\]
Ordinary least squares solves \\(\hat{\boldsymbol{\beta}} = (X^TX)^{-1}X^Ty\\). Inspect coefficients, their standard errors, \\(t\\)-tests, and \\(R^2\\). The Gauss–Markov theorem makes OLS the best linear unbiased estimator under its assumptions.

### Assumptions (the "LINE" checklist)

- **L**inearity of the relationship.
- **I**ndependence of errors.
- **N**ormality of residuals.
- **E**qual variance (homoscedasticity).

Check with residual plots, Q–Q plots, and leverage diagnostics. Violations call for transformations, robust SEs, or different models.

## Generalized Linear Models

GLMs extend regression to non-normal responses via a link function:
- **Logistic regression** — binary outcomes, logit link.
- **Poisson regression** — counts, log link.

\\[
g(\mathbb{E}[y]) = X\boldsymbol{\beta}.
\\]

## Inference vs. Prediction

| Goal | Emphasis |
|---|---|
| Inference | interpretable coefficients, confidence intervals, hypothesis tests |
| Prediction | out-of-sample accuracy, possibly black-box models |

State which you are doing — they have different standards of success.

## Time Series and Hierarchical Models

- **ARIMA / SARIMA** for autocorrelated series; check stationarity (differencing, ADF test).
- **Mixed-effects / hierarchical models** for grouped data (students within schools), sharing strength across groups.
- **Bayesian models** quantify full posterior uncertainty — see [Bayesian Inference](../../math/probability/bayes.md).

## Example: OLS with statsmodels

```python
import statsmodels.formula.api as smf
import seaborn as sns

df = sns.load_dataset("mpg").dropna()
model = smf.ols("mpg ~ weight + horsepower + C(origin)", data=df).fit()
print(model.summary().tables[1])   # coefficients, std err, p-values
```

## See Also

- [Statistical Estimation](../../math/probability/estimation.md)
- [Hypothesis Testing](../../math/probability/hypothesis-testing.md)
- [Model Evaluation](../ml/evaluation.md)
