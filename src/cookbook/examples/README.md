# Worked Examples

This section is the heart of the cookbook: **complete, worked recipes** that take a concept from theory to running code. Where the earlier chapters explain *what* and *why*, these recipes show *how* — end to end, reproducibly.

## The Recipe Format

Each recipe follows the standardized structure introduced in [Structure of a Recipe](../../guide/structure.md):

1. **Purpose** — the problem it solves.
2. **Background** — the minimal theory needed.
3. **Ingredients** — tools, libraries, prerequisites.
4. **Method** — step-by-step procedure.
5. **Example** — runnable code (Python, MATLAB, and Rust where it fits).
6. **Result** — expected output and interpretation.
7. **Variations** — extensions and related problems.
8. **References** — cross-links and further reading.

## Runnable Code

Many recipes include **Rust** snippets that run directly in the browser — click the ▶ (play) button on the code block to execute them on the Rust Playground. Python and MATLAB examples are meant to be copied into your own environment. All Rust examples are dependency-free (standard library only) so they compile and run as shown, and are checked in CI with `mdbook test`.

## Recipe Index

- [Calculus Recipes](calculus.md) — root finding, numerical differentiation/integration.
- [Probability Recipes](probability.md) — Monte Carlo, Bayesian updating, sampling.
- [Signals and Systems Recipes](signals.md) — FFT spectra, filtering, convolution.
- [Machine Learning Recipes](ml.md) — regression, classification, clustering pipelines.
- [Statics and Dynamics Recipes](mechanics.md) — equilibrium, projectile, vibration.
- [Control Recipes](control.md) — PID tuning, step response, stability.
- [Optimization Recipes](optimization.md) — gradient descent, constrained, least squares.

## How to Use This Section

Browse by topic, copy the recipe closest to your problem, and adapt the **Variations**. Each recipe links back to the theory chapter it draws on — start there if a step is unclear.
