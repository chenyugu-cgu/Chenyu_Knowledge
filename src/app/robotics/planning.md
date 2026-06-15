# Motion Planning

Motion planning finds a collision-free path from start to goal that respects the robot's kinematics, dynamics, and environment. It operates in **configuration space** \\(\mathcal{C}\\), where obstacles become forbidden regions \\(\mathcal{C}_{obs}\\).

## Path vs. Trajectory

- A **path** is a geometric route through \\(\mathcal{C}_{free}\\) (no timing).
- A **trajectory** adds a time parameterization (velocities, accelerations) respecting actuator limits.

## Graph-Based Planning

Discretize the space into a grid or graph and search:
- **Dijkstra** — shortest path, explores uniformly.
- **A\\(^*\\)** — Dijkstra guided by an admissible heuristic \\(h\\); optimal and far faster.
- **D\\(^*\\) / D\\(^*\\) Lite** — replan efficiently as the map changes.

The cost-to-go estimate \\(f(n) = g(n) + h(n)\\) drives A\\(^*\\)'s efficiency.

## Sampling-Based Planning

In high dimensions, grids explode. Sampling-based planners scale far better:
- **PRM (Probabilistic Roadmap)** — sample configurations, connect neighbors, then query. Good for multi-query.
- **RRT (Rapidly-exploring Random Tree)** — grow a tree by random sampling and steering; fast for single queries.
- **RRT\\(^*\\)** — asymptotically optimal variant that rewires for shorter paths.

These are **probabilistically complete**: they find a solution if one exists, given enough samples.

## Potential Fields and Optimization

- **Artificial potential fields** pull toward the goal and push from obstacles — reactive and fast, but can stick in local minima.
- **Trajectory optimization** (CHOMP, TrajOpt) minimizes a cost (smoothness + obstacle penalty) directly, producing smooth, dynamically feasible trajectories.

## Trajectory Generation

Once a path is found, fit smooth time profiles — cubic/quintic polynomials, trapezoidal velocity, or **splines** — that honor velocity, acceleration, and jerk limits.

## Planning Under Uncertainty

Real robots face sensor and actuation noise. POMDPs, belief-space planning, and receding-horizon (MPC) approaches plan while accounting for what the robot does **not** know.

## See Also

- [Sensing and Perception](sensing.md)
- [Robot Control](control.md)
- [Metaheuristic Methods](../../cs/optimization/metaheuristics.md)
