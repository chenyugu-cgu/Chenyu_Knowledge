# System Identification

Every model-based controller needs a model, and system identification is how models are built from data. Apply an input, measure the response, choose a model structure, and estimate its parameters so that the model's predictions match what was observed. Doing this well takes statistics (how much to trust an estimate), linear algebra (least squares and its relatives), signal design (inputs rich enough to reveal the dynamics), and a family of model structures that runs from linear difference equations to neural networks.

This subsection follows the graduate course *Statistical Model Estimation* (Georgia Tech ME 8873), with Ljung's *System Identification: Theory for the User* as the reference text.

## Chapters

**Estimation foundations**
1. [Parameter Estimation and Hypothesis Testing](statistical-inference.md)
2. [Least Squares and Recursive Least Squares](least-squares.md)
3. [PCA, ICA and Partial Least Squares](latent-variable-models.md)
4. [Observers and the Kalman Filter for Estimation](state-estimation.md)

**Identifying dynamic systems**
5. [Model Structures and Prediction-Error Methods](model-structures.md)
6. [Neural-Network Models](neural-models.md)
7. [Informative Experiments, Persistent Excitation and Asymptotic Properties](identifiability.md)
8. [Input Design](input-design.md)

## The Identification Loop

1. **Experiment design**: choose an input (PRBS, multisine) that excites the dynamics of interest.
2. **Model structure**: FIR, ARX, ARMAX, output-error, Box–Jenkins, state-space or nonlinear.
3. **Estimation**: least squares or prediction-error minimization.
4. **Validation**: residual analysis, cross-validation, uncertainty of the estimates.
5. If the model fails validation, revise the experiment or the structure and repeat.

## Related Pages

- [Linear Systems Theory](../linear/README.md), especially [Optimal Estimation and the Kalman Filter](../linear/kalman-filter.md).
- [Random Processes](../../../math/random-processes/README.md) for spectra and stochastic signals.
- [Machine Learning](../../../cs/ml/README.md) for the learning-theory view of the same problems.
