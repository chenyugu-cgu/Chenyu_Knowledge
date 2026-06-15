# Algorithms and Data Structures

Algorithms are step-by-step procedures for solving problems; data structures organize information so algorithms can act on it efficiently. Together they are the foundation of all computing and the basis for reasoning about *how fast* and *how much memory* a program needs.

## Why It Matters for Engineers

- **Robotics** — path planning is graph search ([Motion Planning](../../app/robotics/planning.md)).
- **Scientific computing** — efficient data structures make large simulations feasible.
- **Data science / ML** — algorithmic complexity decides what scales.
- **Embedded systems** — tight memory and time budgets demand efficient algorithms.

## The Central Question: Complexity

We measure cost by how runtime/space grow with input size \\(n\\), using **big-O** notation. An \\(O(n\log n)\\) algorithm beats an \\(O(n^2)\\) one decisively as \\(n\\) grows — often the difference between seconds and hours. See [Complexity and Analysis](complexity.md).

## Chapter Map

- [Data Structures](data-structures.md) — arrays, lists, trees, hashes, heaps.
- [Sorting and Searching](sorting-searching.md) — the classic algorithms.
- [Graph Algorithms](graph-algorithms.md) — traversal, shortest paths, spanning trees.
- [Complexity and Analysis](complexity.md) — big-O, P vs. NP.
- [Dynamic Programming](dynamic-programming.md) — solving by overlapping subproblems.

## Connections

Builds on [Discrete Mathematics](../../math/discrete/README.md) (graphs, recurrences, proofs) and supports everything in [Scientific Computing](../scientific-computing/README.md) and [Machine Learning](../ml/README.md).
