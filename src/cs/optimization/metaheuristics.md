# Metaheuristic Methods

When the objective is nonconvex, noisy, discontinuous, or has no usable gradient, **metaheuristics** offer derivative-free global search. They trade optimality guarantees for broad applicability, balancing **exploration** (search widely) and **exploitation** (refine the best).

## When to Use Them

- Combinatorial problems (routing, scheduling, layout).
- Black-box objectives (simulation outputs, no gradient).
- Highly multimodal landscapes where local methods get trapped.

They are a last resort when structure cannot be exploited — slower and without proofs, but remarkably general.

## Simulated Annealing

Inspired by metallurgical cooling. Accept worse moves with probability
\\[
P = \exp\!\left(-\frac{\Delta f}{T}\right),
\\]
gradually lowering the "temperature" \\(T\\). High \\(T\\) explores freely; low \\(T\\) settles into a minimum. With a slow enough schedule it converges to the global optimum in theory.

## Genetic Algorithms

Maintain a **population** of candidate solutions and evolve it:
1. **Selection** — favor high-fitness individuals.
2. **Crossover** — recombine pairs to make offspring.
3. **Mutation** — randomly perturb genes for diversity.

Powerful for combinatorial and mixed problems; needs careful encoding and operator design.

## Particle Swarm Optimization

Particles fly through the search space, pulled toward their own best position and the swarm's best:
\\[
\mathbf{v}_{i} \leftarrow w\mathbf{v}_i + c_1 r_1(\mathbf{p}_i - \mathbf{x}_i) + c_2 r_2(\mathbf{g} - \mathbf{x}_i), \qquad \mathbf{x}_i \leftarrow \mathbf{x}_i + \mathbf{v}_i.
\\]
Simple, few parameters, effective on continuous landscapes.

## Other Methods

- **Differential evolution** — vector differences drive mutation; strong for continuous global optimization.
- **Ant colony optimization** — pheromone trails for routing/graph problems.
- **Bayesian optimization** — build a surrogate (Gaussian process) and optimize an acquisition function; ideal for **expensive** black-box objectives like hyperparameter tuning.

## Caveats

- **No free lunch:** no single method dominates across all problems.
- **No optimality certificate:** you get a good solution, not a proven best.
- **Tuning matters:** population size, cooling rate, and operators strongly affect results.
- Always compare against a problem-specific or convex baseline when one exists.

## See Also

- [Convex Optimization](convex.md) — prefer it whenever the problem allows.
- [Reinforcement Learning](../ml/rl.md)
- [Optimization Recipes](../../cookbook/examples/optimization.md)
