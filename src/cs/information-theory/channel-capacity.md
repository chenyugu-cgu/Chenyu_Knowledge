# Channel Capacity

Channel capacity is the maximum rate at which information can be sent over a noisy channel with arbitrarily small error. Shannon's noisy-channel coding theorem is one of the most surprising results in science: reliable communication is possible **despite** noise, up to a precise limit.

## Channel Capacity

The capacity is the maximum mutual information between input and output over all input distributions:
\\[
C = \max_{p(x)} I(X; Y) \quad\text{bits per use}.
\\]
Below \\(C\\), codes exist with vanishing error; above \\(C\\), reliable communication is impossible.

## The Shannon–Hartley Theorem

For a continuous channel of bandwidth \\(B\\) with signal-to-noise ratio \\(S/N\\):
\\[
C = B\log_2\!\left(1 + \frac{S}{N}\right) \quad\text{bits/second}.
\\]
Capacity grows linearly with bandwidth and logarithmically with SNR — why more spectrum helps more than more power, and the guiding equation of modern communications (Wi-Fi, 5G, deep-space links).

## Channel Coding (Error Correction)

To approach capacity we add **redundancy** so errors can be detected and corrected:

| Code | Use |
|---|---|
| Parity / checksum | error detection |
| Hamming | correct single-bit errors |
| Reed–Solomon | burst errors (CDs, QR codes, storage) |
| Convolutional / Viterbi | streaming, wireless |
| **Turbo / LDPC** | near-capacity (4G/5G, Wi-Fi) |

Modern LDPC and turbo codes operate within a fraction of a decibel of the Shannon limit.

## The Fundamental Trade

Communication trades **bandwidth, power (SNR), and reliability**. Shannon's theorem makes the trade exact and tells engineers the best that is achievable — a benchmark every real system is measured against.

## Connections

Links to [signal processing](../../eng/electrical/signal-processing.md) and [sampling](../../signals/sampling.md) (rate and bandwidth), and to [entropy](entropy.md) (the source side of the same theory).

## See Also

- [Entropy and Information](entropy.md)
- [Source Coding](source-coding.md)
- [Signal Processing](../../eng/electrical/signal-processing.md)
