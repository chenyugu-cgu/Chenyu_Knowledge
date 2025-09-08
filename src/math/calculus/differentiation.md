
# Differentiation

Differentiation is one of the two fundamental operations in calculus (the other being integration). It provides a rigorous method for describing the instantaneous rate of change of a function, and it is essential for understanding how quantities vary in mathematics, science, and engineering.

## What is Differentiation?

At its core, differentiation answers the question: "How does a function change as its input changes?" If you imagine the graph of a function \\( y = f(x) \\), the derivative at a point gives the slope of the tangent line to the curve at that point. This slope represents the instantaneous rate of change of \\( y \\) with respect to \\( x \\).

### Formal Definition (Limit Definition)

The derivative of a function \\( f(x) \\) at a point \\( x = a \\) is defined as the following limit (if it exists):

\\[
f'(a) = \lim_{h \to 0} \frac{f(a + h) - f(a)}{h}
\\]

This expression captures the idea of the average rate of change over an interval \\( h \\) shrinking down to an instantaneous rate as \\( h \\to 0 \\).

#### Example

Let \\( f(x) = x^2 \\). The derivative at \\( x \\) is:
\\[
f'(x) = \lim_{h \to 0} \frac{(x + h)^2 - x^2}{h}
      = \lim_{h \to 0} \frac{x^2 + 2xh + h^2 - x^2}{h}
      = \lim_{h \to 0} \frac{2xh + h^2}{h}
      = \lim_{h \to 0} (2x + h)
      = 2x
\\]

## Basic Rules of Differentiation

To make differentiation practical, several rules allow us to compute derivatives efficiently:

- **Power Rule:** If \\( f(x) = x^n \\), then \\( f'(x) = n x^{n-1} \\).
- **Constant Multiple Rule:** \\( \frac{d}{dx} [c f(x)] = c f'(x) \\), where \\( c \\) is a constant.
- **Sum Rule:** \\( \frac{d}{dx} [f(x) + g(x)] = f'(x) + g'(x) \\).

### Product Rule

If \\( f(x) \\) and \\( g(x) \\) are differentiable:
\\[
\frac{d}{dx} [f(x) g(x)] = f'(x) g(x) + f(x) g'(x)
\\]

**Example:** If \\( f(x) = x^2 \\), \\( g(x) = \sin x \\):
\\[
\frac{d}{dx} [x^2 \sin x] = 2x \sin x + x^2 \cos x
\\]

### Quotient Rule

If \\( f(x) \\) and \\( g(x) \\) are differentiable and \\( g(x) \neq 0 \\):
\\[
\frac{d}{dx} \left[ \frac{f(x)}{g(x)} \right] = \frac{f'(x) g(x) - f(x) g'(x)}{[g(x)]^2}
\\]

**Example:** If \\( f(x) = x \\), \\( g(x) = x^2 + 1 \\):
\\[
\frac{d}{dx} \left[ \frac{x}{x^2 + 1} \right] = \frac{1 \cdot (x^2 + 1) - x \cdot 2x}{(x^2 + 1)^2} = \frac{x^2 + 1 - 2x^2}{(x^2 + 1)^2} = \frac{1 - x^2}{(x^2 + 1)^2}
\\]

### Chain Rule

For a composite function \\( y = f(g(x)) \\):
\\[
\frac{dy}{dx} = f'(g(x)) \cdot g'(x)
\\]

**Example:** If \\( y = \sin(x^2) \\), then \\( f(u) = \sin u \\), \\( u = x^2 \\):
\\[
\frac{dy}{dx} = \cos(x^2) \cdot 2x
\\]

## Higher-Order Derivatives

The process of differentiation can be repeated. The second derivative \\( f''(x) \\) is the derivative of \\( f'(x) \\), and so on. Higher-order derivatives are important in physics (e.g., acceleration is the second derivative of position) and in describing curvature and concavity.

**Example:** For \\( f(x) = x^3 \\):
\\[
f'(x) = 3x^2 \\
f''(x) = 6x \\
f'''(x) = 6
\\]

## Applications in Science and Engineering

- **Velocity and Acceleration:** In physics, if \\( s(t) \\) is the position of an object at time \\( t \\), then velocity \\( v(t) = s'(t) \\), and acceleration \\( a(t) = v'(t) = s''(t) \\).
- **Optimization:** Differentiation helps find maxima and minima of functions (e.g., maximizing profit, minimizing cost).
- **Sensitivity Analysis:** The derivative describes how sensitive a function is to small changes in its input—a key idea in engineering and data science.

## Cookbook Structure for Differentiation Recipes

Each recipe in this section follows a standardized structure:

- **Purpose:** What problem does this recipe solve?
- **Background:** Brief context or theory.
- **Ingredients:** What you need (formulas, properties, prerequisites).
- **Method:** Step-by-step procedure for differentiation.
- **Example:** A worked example with detailed math.
- **Result:** The outcome and interpretation.
- **Variations:** Extensions, generalizations, or related techniques.
- **References:** Sources for further reading.

This format helps you quickly find, understand, and apply differentiation techniques to a wide range of problems.
