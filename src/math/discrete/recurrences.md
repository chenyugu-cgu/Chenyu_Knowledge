# Recurrence Relations

A **recurrence** defines each term of a sequence from earlier terms. Recurrences describe recursive algorithms, discrete-time systems, and combinatorial counts.

## Linear Recurrences with Constant Coefficients

For \\(a_n = c_1 a_{n-1} + c_2 a_{n-2} + \cdots\\), substitute \\(a_n = r^n\\) to get the **characteristic equation** — exactly analogous to [linear ODEs](../diffeq/second-order.md). Distinct roots give \\(a_n = \sum_i A_i r_i^n\\); repeated roots introduce polynomial factors \\(n^k r^n\\).

**Example (Fibonacci).** \\(F_n = F_{n-1} + F_{n-2}\\) has characteristic equation \\(r^2 = r + 1\\), roots \\(\varphi = \frac{1+\sqrt5}{2}\\) and \\(\psi = \frac{1-\sqrt5}{2}\\), giving Binet's formula
\\[
F_n = \frac{\varphi^n - \psi^n}{\sqrt5}.
\\]

## Divide-and-Conquer Recurrences

Algorithms that split a problem of size \\(n\\) into \\(a\\) subproblems of size \\(n/b\\) plus \\(O(n^d)\\) work obey
\\[
T(n) = a\,T(n/b) + O(n^d).
\\]

### The Master Theorem

\\[
T(n) = \begin{cases}
O(n^d) & a < b^d,\\
O(n^d \log n) & a = b^d,\\
O(n^{\log_b a}) & a > b^d.
\end{cases}
\\]
For example, merge sort (\\(a=2, b=2, d=1\\)) hits the middle case: \\(O(n\log n)\\). See [Complexity and Analysis](../../cs/algorithms/complexity.md).

## Generating Functions

Encode a sequence as coefficients of a power series \\(G(x) = \sum a_n x^n\\); algebraic manipulation of \\(G\\) solves the recurrence and yields closed forms — a bridge to [series](../calculus/series.md) and [complex analysis](../complex/README.md).

## Applications

Algorithm runtime analysis, [digital filters](../../signals/z-transform.md) (difference equations are recurrences), compound interest, and population models.

## See Also

- [Complexity and Analysis](../../cs/algorithms/complexity.md)
- [Z-Transform](../../signals/z-transform.md)
- [Second-Order Linear ODEs](../diffeq/second-order.md)
