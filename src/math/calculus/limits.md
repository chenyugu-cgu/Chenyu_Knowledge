
# Limits and Continuity

Limits and continuity are foundational concepts in calculus, forming the basis for defining derivatives and integrals. Understanding limits allows us to rigorously describe how functions behave as their inputs approach specific values, while continuity characterizes when functions behave predictably without sudden jumps or breaks.

## Definition of a Limit (Epsilon-Delta Formulation)

Let \\( f(x) \\) be a function defined on an open interval containing \\( c \\), except possibly at \\( c \\) itself. We say that the limit of \\( f(x) \\) as \\( x \\) approaches \\( c \\) is \\( L \\), and write
\\[
    \lim_{x \to c} f(x) = L
\\]
if for every \\( \varepsilon > 0 \\) there exists a \\( \delta > 0 \\) such that whenever \\( 0 < |x - c| < \delta \\), it follows that \\( |f(x) - L| < \varepsilon \\).

In words: as \\( x \\) gets arbitrarily close (but not equal) to \\( c \\), \\( f(x) \\) gets arbitrarily close to \\( L \\).

## Examples of Limits for Simple Functions

**Example 1:**
\\[
    \lim_{x \to 2} (3x + 1) = 7
\\]
because as \\( x \\) approaches 2, \\( 3x + 1 \\) approaches 7.

**Example 2:**
\\[
    \lim_{x \to 0} \sin(x) = 0
\\]
since the sine function is continuous everywhere.

**Example 3 (Removable Discontinuity):**
Let
\\[
    f(x) = \frac{x^2 - 1}{x - 1}
\\]
for \\( x \neq 1 \\). Then
\\[
    \lim_{x \to 1} f(x) = \lim_{x \to 1} \frac{(x-1)(x+1)}{x-1} = \lim_{x \to 1} (x+1) = 2
\\]
even though \\( f(1) \\) is not defined.

## One-Sided Limits and Infinite Limits

The **left-hand limit** of \\( f(x) \\) as \\( x \\) approaches \\( c \\) is denoted
\\[
    \lim_{x \to c^-} f(x)
\\]
and considers values of \\( x \\) less than \\( c \\).

The **right-hand limit** is denoted
\\[
    \lim_{x \to c^+} f(x)
\\]
and considers values of \\( x \\) greater than \\( c \\).

If the left- and right-hand limits exist and are equal, then the (two-sided) limit exists.

**Infinite limits** occur when \\( f(x) \\) grows arbitrarily large as \\( x \\) approaches \\( c \\):
\\[
    \lim_{x \to c} f(x) = \infty
\\]
means that for every \\( M > 0 \\), there exists \\( \delta > 0 \\) such that \\( 0 < |x - c| < \delta \implies f(x) > M \\).

## Definition of Continuity

A function \\( f(x) \\) is **continuous at a point** \\( c \\) if all three of the following conditions are satisfied:

1. \\( f(c) \\) is defined.
2. \\( \lim_{x \to c} f(x) \\) exists.
3. \\( \lim_{x \to c} f(x) = f(c) \\).

If a function is continuous at every point in an interval, it is said to be **continuous on that interval**.

## Common Theorems

### Intermediate Value Theorem (IVT)
If \\( f \\) is continuous on the closed interval \\( [a, b] \\), and \\( N \\) is any number between \\( f(a) \\) and \\( f(b) \\), then there exists at least one \\( c \in [a, b] \\) such that \\( f(c) = N \\).

### Extreme Value Theorem (EVT)
If \\( f \\) is continuous on the closed interval \\( [a, b] \\), then \\( f \\) attains both a maximum and a minimum value on \\( [a, b] \\); that is, there exist \\( c, d \in [a, b] \\) such that
\\[
    f(c) \leq f(x) \leq f(d)
\\]
for all \\( x \in [a, b] \\).

## Cookbook Overview

The recipes in this section will present worked problems using the following structure:

- **Purpose:** What the recipe helps you achieve.
- **Background:** Mathematical context and definitions.
- **Ingredients:** The functions, values, or theorems you need.
- **Method:** Step-by-step solution process.
- **Example:** A fully worked sample problem.
- **Result:** The final answer and its significance.
- **Variations:** Related problems or extensions.
- **References:** Sources for further reading.

This format is designed to help you master limits and continuity by connecting concepts, techniques, and applications.
