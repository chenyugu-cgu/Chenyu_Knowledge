# Source Coding

Source coding is **data compression** — representing information with as few bits as possible. Shannon's source coding theorem sets the hard limit: you cannot compress below the entropy without losing information.

## The Limit

For a source with entropy \\(H(X)\\) bits/symbol, any lossless code needs at least \\(H(X)\\) bits/symbol on average:
\\[
\bar{L} \ge H(X).
\\]
Good codes approach this bound; it cannot be beaten.

## Lossless Compression

Reconstructs the original exactly. Key methods:

| Method | Idea |
|---|---|
| **Huffman coding** | optimal prefix code; short codes for frequent symbols |
| **Arithmetic coding** | encodes a whole message as one fraction; near-entropy |
| **Lempel–Ziv (LZ77/LZW)** | dictionary of repeated substrings (ZIP, PNG, GIF) |
| **Run-length encoding** | runs of repeats → (value, count) |

**Prefix (instantaneous) codes** — no codeword is a prefix of another — are uniquely decodable and satisfy the **Kraft inequality** \\(\sum 2^{-\ell_i} \le 1\\).

## Lossy Compression

Discards perceptually unimportant information for far higher ratios — essential for media:
- **JPEG** — DCT + quantization of image blocks.
- **MP3/AAC** — psychoacoustic models drop inaudible frequencies.
- **H.264/H.265** — motion compensation + transform coding for video.

Lossy methods trade fidelity for size, governed by **rate–distortion theory** (minimum bits for a tolerated distortion).

## Example: Huffman Intuition

For symbols with probabilities {A:0.5, B:0.25, C:0.125, D:0.125}, Huffman assigns lengths {1,2,3,3} bits, giving \\(\bar{L} = 1.75\\) bits — exactly the entropy. Frequent symbols get shorter codes.

## See Also

- [Entropy and Information](entropy.md)
- [Channel Capacity](channel-capacity.md)
- [Signal Processing](../../eng/electrical/signal-processing.md) — transform coding.
