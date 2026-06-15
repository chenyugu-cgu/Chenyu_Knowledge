# Circuit Laws

Circuit analysis reduces a network of elements to a set of solvable equations using two foundational laws plus a handful of powerful theorems.

## Ohm's Law

\\[
V = IR, \qquad P = VI = I^2 R = \frac{V^2}{R}.
\\]

## Kirchhoff's Laws

- **Kirchhoff's Current Law (KCL):** the algebraic sum of currents into any node is zero (charge conservation): \\(\sum i = 0\\).
- **Kirchhoff's Voltage Law (KVL):** the algebraic sum of voltages around any closed loop is zero (energy conservation): \\(\sum v = 0\\).

These two laws, combined with element relations, fully determine any circuit.

## Series and Parallel Combinations

\\[
R_{\text{series}} = \sum R_i, \qquad \frac{1}{R_{\text{parallel}}} = \sum\frac{1}{R_i}.
\\]
Capacitors combine **oppositely** to resistors; inductors combine like resistors.

### Dividers

\\[
\text{Voltage divider: } v_k = v\,\frac{R_k}{\sum R}, \qquad
\text{Current divider: } i_k = i\,\frac{G_k}{\sum G}.
\\]

## Systematic Methods

- **Nodal analysis:** write KCL at each node in terms of node voltages → solve a linear system \\(G\mathbf{v} = \mathbf{i}\\).
- **Mesh analysis:** write KVL around each mesh in terms of loop currents → \\(R\mathbf{i} = \mathbf{v}\\).

Both reduce to solving a matrix equation — see [Matrix Operations](../../math/linear-algebra/matrices.md).

## Network Theorems

- **Superposition:** in a linear circuit, the response is the sum of responses to each independent source acting alone.
- **Thévenin / Norton:** any linear two-terminal network reduces to a single source plus a series (Thévenin) or parallel (Norton) resistance: \\(V_{th} = I_N R_{th}\\).
- **Maximum power transfer:** a load receives maximum power when \\(R_L = R_{th}\\).

## Worked Example: Thévenin Equivalent

For a 12 V source with a 4 Ω and 6 Ω divider feeding a load at the 6 Ω node:
\\[
V_{th} = 12\cdot\frac{6}{4+6} = 7.2\ \text{V}, \quad R_{th} = 4\,\|\,6 = 2.4\ \Omega.
\\]
Maximum power to a matched load: \\(P_{\max} = V_{th}^2/(4R_{th}) = 5.4\\) W.

## See Also

- [AC and DC Analysis](ac-dc.md)
- [Matrix Operations](../../math/linear-algebra/matrices.md)
