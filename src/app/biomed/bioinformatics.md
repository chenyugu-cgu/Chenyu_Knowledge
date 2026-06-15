# Bioinformatics

Bioinformatics applies computation, statistics, and algorithms to biological data — DNA/RNA/protein sequences, structures, and large-scale "omics" datasets. It is where [algorithms](../../cs/algorithms/README.md), [machine learning](../../cs/ml/README.md), and [biochemistry](../../physics/chemistry/biochemistry.md) meet.

## Biological Data

The central data type is **sequence**: DNA (A,C,G,T), RNA, and proteins (20 amino acids). Modern sequencing produces enormous datasets (a human genome is ~3 billion base pairs), demanding efficient storage and algorithms.

## Sequence Alignment

Comparing sequences reveals evolutionary relationships and function. Alignment is a classic **[dynamic programming](../../cs/algorithms/dynamic-programming.md)** problem:
- **Needleman–Wunsch** — global alignment.
- **Smith–Waterman** — local alignment.
- **BLAST** — fast heuristic search against databases.

Scoring uses substitution matrices (BLOSUM, PAM) and gap penalties.

## Genomics and Sequencing

- **Genome assembly** — reconstruct a genome from short reads (a graph problem — de Bruijn graphs).
- **Variant calling** — find differences from a reference (SNPs, indels).
- **Gene expression** — RNA-seq quantifies transcription; analysis is high-dimensional statistics.

## Structure and Function

Protein **structure prediction** — long an open challenge — was transformed by deep learning (AlphaFold), predicting 3-D structure from sequence with remarkable accuracy. Structure informs function and drug design.

## Machine Learning in Biology

[ML](../../cs/ml/README.md) classifies disease from genomic/expression data, predicts drug response, and finds patterns in high-dimensional omics — with careful attention to the **small-n, large-p** regime (few samples, many features) where overfitting and [multiple testing](../../math/probability/hypothesis-testing.md) are serious risks. Dimensionality reduction (PCA) and [regularization](../../cs/ml/regularization.md) are essential.

## Applications

Personalized medicine, drug discovery, evolutionary biology, cancer genomics, and understanding disease mechanisms.

## See Also

- [Dynamic Programming](../../cs/algorithms/dynamic-programming.md)
- [Biochemistry](../../physics/chemistry/biochemistry.md)
- [Machine Learning](../../cs/ml/README.md)
