# Dynamic Programming

Dynamic programming (DP) solves problems by breaking them into **overlapping subproblems** and storing each subproblem's answer to avoid recomputation. It turns exponential brute force into polynomial time.

## When DP Applies

Two ingredients are required:
1. **Optimal substructure** — the optimal solution is built from optimal solutions of subproblems.
2. **Overlapping subproblems** — the same subproblems recur many times.

(Without overlap, plain divide-and-conquer suffices.)

## Two Styles

- **Top-down (memoization)** — recurse naturally, cache results.
- **Bottom-up (tabulation)** — fill a table from base cases upward.

Both achieve the same complexity; tabulation avoids recursion overhead, memoization is closer to the recursive definition.

## Classic Example: Fibonacci

Naive recursion is \\(O(2^n)\\) because it recomputes; caching makes it \\(O(n)\\):

```rust
fn fib(n: usize) -> u64 {
    let mut dp = vec![0u64; n + 1];
    if n >= 1 { dp[1] = 1; }
    for i in 2..=n {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    dp[n]
}

fn main() {
    println!("{}", fib(50)); // 12586269025
}
```

## Canonical DP Problems

| Problem | State / recurrence |
|---|---|
| 0/1 Knapsack | \\(dp[i][w]\\) = best value using first \\(i\\) items within weight \\(w\\) |
| Longest common subsequence | \\(dp[i][j]\\) on prefixes |
| Edit distance | insert/delete/replace costs |
| Coin change | min coins for each amount |
| Matrix-chain order | optimal parenthesization |

## Designing a DP

1. Define the **state** (what subproblem a table entry represents).
2. Write the **recurrence** linking states.
3. Set **base cases**.
4. Choose an **evaluation order** so dependencies are ready.
5. (Optional) reconstruct the solution by backtracking through the table.

## Relation to Control and RL

DP is exactly Bellman's principle of optimality — the foundation of [optimal control](../../eng/control/optimal.md) and [reinforcement learning](../ml/rl.md), where value functions are computed by the same recurrence.

## See Also

- [Complexity and Analysis](complexity.md)
- [Optimal Control](../../eng/control/optimal.md)
- [Reinforcement Learning](../ml/rl.md)
