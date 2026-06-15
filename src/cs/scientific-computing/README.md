# Scientific Computing

Scientific computing is the discipline of solving mathematical and engineering problems numerically on computers — simulation, modeling, and large-scale computation. It bridges [numerical methods](../../math/numerical/README.md), [algorithms](../algorithms/README.md), and high-performance hardware.

## The Core Concerns

1. **Accuracy** — numbers are finite; rounding and truncation introduce error. See [Floating-Point and Error](floating-point.md).
2. **Stability** — does error grow or stay bounded as a computation proceeds?
3. **Efficiency** — can it run on available time and memory? See [Performance and Parallelism](performance.md).
4. **Reproducibility** — same inputs, same results, documented and version-controlled.

## What It Powers

- Engineering simulation: [FEA](../../math/numerical/fem.md), [CFD](../../eng/fluid/turbulence.md), circuit and multibody simulation.
- Solving [differential equations](../../math/diffeq/README.md) too complex for closed form.
- Large [linear systems](linear-systems.md) at the heart of nearly every method.
- Data-intensive [machine learning](../ml/README.md) and [data science](../data/README.md).

## Chapter Map

- [Floating-Point and Error](floating-point.md)
- [Solving Linear Systems](linear-systems.md)
- [Performance and Parallelism](performance.md)

## Tools

NumPy/SciPy and Julia for prototyping; C/C++/Fortran and Rust for performance; BLAS/LAPACK for dense linear algebra; MPI/OpenMP/CUDA for parallelism.

## See Also

- [Numerical Methods](../../math/numerical/README.md)
- [Matrix Operations](../../math/linear-algebra/matrices.md)
