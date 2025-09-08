# Notation and Conventions

This book follows a consistent set of notation rules to ensure clarity and uniformity throughout all chapters. Below we detail the conventions used for mathematical notation, inline and display math, Greek letters and symbols, indexing, units and dimensions, as well as code examples.

## Mathematical Notation

- **Vectors** are denoted by **bold lowercase** letters, for example, \\(\mathbf{x}\\), \\(\mathbf{y}\\), and \\(\mathbf{z}\\).
- **Matrices** are represented by **bold uppercase** letters, such as \\(\mathbf{A}\\), \\(\mathbf{B}\\), and \\(\mathbf{M}\\).
- **Scalars** are written in *italic* font, for example, \\(x\\), \\(y\\), and \\(z\\).
- **Sets** are indicated using calligraphic letters, e.g., \\(\mathcal{D}\\), \\(\mathcal{S}\\), and \\(\mathcal{X}\\).

## Inline vs Display Math

- Inline mathematical expressions are enclosed within `\\(...\\)`, for example, \\(a^2 + b^2 = c^2\\).
- Display equations that require emphasis or are too long for inline use are enclosed within `\\[...\\]`, such as:
  \\[
  \nabla f(\mathbf{x}) = \begin{bmatrix}
  \frac{\partial f}{\partial x_1} \\
  \frac{\partial f}{\partial x_2} \\
  \vdots \\
  \frac{\partial f}{\partial x_n}
  \end{bmatrix}
  \\]

## Greek Letters and Common Symbols

The following Greek letters and symbols are frequently used with specific meanings:

- \\(\alpha, \beta, \lambda\\): Typically used to denote coefficients or parameters in models.
- \\(\mu, \sigma\\): Represent the mean and standard deviation of a distribution, respectively.
- \\(\nabla\\): Denotes the gradient operator, used in optimization and calculus contexts.

These symbols are consistently used with these meanings unless otherwise specified.

## Indexing Conventions

- Programming examples use **zero-based indexing**, meaning indices start at 0.
- Mathematical derivations and theoretical discussions use **one-based indexing**, where indices start at 1.

This distinction helps bridge understanding between code implementations and mathematical theory.

## Units and Dimensions

- SI units are used by default throughout the book.
- Dimensions are explicitly indicated when relevant to the discussion, ensuring clarity in physical quantities and measurements.

## Code Conventions

- Code examples are provided in Python, MATLAB, and Rust to illustrate concepts across different programming environments.
- All code snippets are enclosed in Markdown fenced code blocks specifying the language, for example:

```python
# Python example
def add(a, b):
    return a + b
```

```matlab
% MATLAB example
function c = add(a, b)
    c = a + b;
end
```

```rust
// Rust example
fn add(a: i32, b: i32) -> i32 {
    a + b
}
```

By adhering to these conventions, the book maintains consistency and readability across all chapters and topics.
