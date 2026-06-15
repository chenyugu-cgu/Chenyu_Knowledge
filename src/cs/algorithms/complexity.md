# Complexity and Analysis

Complexity analysis predicts how an algorithm's running time and memory scale with input size — letting us compare algorithms before running them and know what will scale.

## Asymptotic Notation

| Notation | Bound | Meaning |
|---|---|---|
| \\(O(f)\\) | upper | grows no faster than \\(f\\) |
| \\(\Omega(f)\\) | lower | grows at least as fast as \\(f\\) |
| \\(\Theta(f)\\) | tight | both bounds |

Constants and lower-order terms are dropped: \\(3n^2 + 5n + 7 = \Theta(n^2)\\).

## Common Growth Rates

\\[
O(1) < O(\log n) < O(n) < O(n\log n) < O(n^2) < O(2^n) < O(n!).
\\]
The gap is dramatic: at \\(n = 10^6\\), \\(n\log n\\) is feasible while \\(n^2\\) is \\(10^{12}\\) operations and \\(2^n\\) is hopeless.

## Analyzing Algorithms

- **Loops** multiply; nested loops over \\(n\\) give \\(O(n^2)\\).
- **Divide and conquer** uses the [Master Theorem](../../math/discrete/recurrences.md).
- **Amortized analysis** averages cost over a sequence (e.g. dynamic-array append is \\(O(1)\\) amortized despite occasional \\(O(n)\\) resizes).
- **Best / average / worst case** can differ (quicksort: \\(O(n\log n)\\) average, \\(O(n^2)\\) worst).

## Space Complexity

Memory matters too — recursion depth, auxiliary arrays, and in-place vs. out-of-place all count, and dominate on memory-constrained [embedded systems](../../eng/mechatronics/microcontrollers.md).

## Tractability: P vs. NP

- **P** — solvable in polynomial time.
- **NP** — solutions verifiable in polynomial time.
- **NP-complete** — the hardest in NP (SAT, TSP, knapsack); no known polynomial algorithm.

Whether \\(P = NP\\) is the most famous open problem in computer science. For NP-hard problems in practice, we use heuristics, approximation, or [metaheuristics](../optimization/metaheuristics.md).

## See Also

- [Recurrence Relations](../../math/discrete/recurrences.md)
- [Dynamic Programming](dynamic-programming.md)
- [Metaheuristic Methods](../optimization/metaheuristics.md)
