# Data Structures

A data structure organizes data to support specific operations efficiently. Choosing the right one is often more important than clever code.

## Linear Structures

| Structure | Access | Insert/Delete | Notes |
|---|---|---|---|
| Array | \\(O(1)\\) index | \\(O(n)\\) | contiguous, cache-friendly |
| Dynamic array | \\(O(1)\\) | \\(O(1)\\) amortized append | doubles capacity |
| Linked list | \\(O(n)\\) | \\(O(1)\\) at a known node | pointer-based |
| Stack | — | \\(O(1)\\) push/pop | LIFO |
| Queue / deque | — | \\(O(1)\\) | FIFO |

## Hash Tables

A **hash table** maps keys to values via a hash function, giving \\(O(1)\\) average insert/lookup. Collisions are handled by chaining or open addressing. The backbone of dictionaries, caches, and de-duplication — but worst case degrades to \\(O(n)\\) with poor hashing.

## Trees

- **Binary search tree (BST)** — ordered; \\(O(\log n)\\) operations when balanced.
- **Balanced trees** (AVL, red-black) — guarantee \\(O(\log n)\\) by rebalancing.
- **Heaps** — partially ordered; \\(O(1)\\) peek-min, \\(O(\log n)\\) insert/extract — the basis of priority queues and [Dijkstra's algorithm](graph-algorithms.md).
- **Tries** — prefix trees for strings.
- **B-trees** — wide, shallow trees for databases and filesystems.

## Choosing a Structure

Match the structure to the dominant operation: frequent lookups by key → hash table; ordered range queries → balanced BST; repeatedly extract the smallest → heap; LIFO/FIFO scheduling → stack/queue.

## Example: A Min-Heap in Rust (runnable)

```rust
use std::collections::BinaryHeap;
use std::cmp::Reverse;

fn main() {
    // BinaryHeap is a max-heap; Reverse turns it into a min-heap.
    let mut heap = BinaryHeap::new();
    for x in [5, 1, 8, 3, 2] {
        heap.push(Reverse(x));
    }
    let mut sorted = Vec::new();
    while let Some(Reverse(x)) = heap.pop() {
        sorted.push(x);
    }
    println!("{:?}", sorted); // [1, 2, 3, 5, 8]
}
```

## See Also

- [Sorting and Searching](sorting-searching.md)
- [Graph Theory](../../math/discrete/graph-theory.md)
- [Complexity and Analysis](complexity.md)
