# Performance and Parallelism

Scientific problems are often huge. Performance engineering and parallelism make intractable computations feasible.

## Where Time Goes

Modern performance is dominated less by raw arithmetic than by **memory access**. The memory hierarchy (registers → L1/L2/L3 cache → RAM → disk) spans orders of magnitude in latency. **Cache-friendly** code — sequential access, blocking, data locality — often beats algorithmically clever but cache-hostile code.

## Profile Before Optimizing

Measure, don't guess. Profilers reveal the actual hot spots; optimizing anything else is wasted effort (Amdahl's law below makes this concrete). First pick a better **algorithm** (a lower [complexity class](../algorithms/complexity.md)), then optimize constants.

## Forms of Parallelism

| Type | Mechanism | Example |
|---|---|---|
| Instruction-level / SIMD | vector units | AVX, NEON |
| Multicore (shared memory) | threads | OpenMP, Rayon |
| Distributed (message passing) | many nodes | MPI |
| GPU (massively data-parallel) | thousands of threads | CUDA, OpenCL |

Matrix operations, stencil PDE solvers, and neural-network training are highly parallel and map beautifully to GPUs.

## Amdahl's and Gustafson's Laws

Speedup is limited by the serial fraction \\(s\\):
\\[
\text{Speedup} \le \frac{1}{s + (1-s)/P}.
\\]
If 10% of the work is serial, no number of processors \\(P\\) exceeds 10× speedup. Gustafson's law is more optimistic for **scaling problem size** with processors.

## Practical Levers

- Use optimized libraries (BLAS/LAPACK, FFTW) — they are cache- and SIMD-tuned.
- Vectorize (NumPy operations, not Python loops).
- Exploit sparsity and structure.
- Choose the right precision (single vs. double) for the accuracy needed.
- Parallelize the embarrassingly parallel parts first.

## See Also

- [Complexity and Analysis](../algorithms/complexity.md)
- [Solving Linear Systems](linear-systems.md)
- [Deep Learning](../ml/deep-learning.md) — GPU-driven training.
