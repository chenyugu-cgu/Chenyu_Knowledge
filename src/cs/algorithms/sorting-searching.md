# Sorting and Searching

Sorting and searching are the most-used algorithms in computing and the classic vehicles for learning algorithm design and analysis.

## Searching

- **Linear search** — \\(O(n)\\); works on any sequence.
- **Binary search** — \\(O(\log n)\\); requires a **sorted** array. Repeatedly halve the search interval.

Binary search is why we sort in the first place: a one-time \\(O(n\log n)\\) sort enables countless \\(O(\log n)\\) lookups.

## Sorting Algorithms

| Algorithm | Average | Worst | Stable | Notes |
|---|---|---|---|---|
| Bubble/insertion | \\(O(n^2)\\) | \\(O(n^2)\\) | yes | fine for tiny/nearly-sorted |
| Merge sort | \\(O(n\log n)\\) | \\(O(n\log n)\\) | yes | needs \\(O(n)\\) extra space |
| Quicksort | \\(O(n\log n)\\) | \\(O(n^2)\\) | no | fast in practice; in-place |
| Heapsort | \\(O(n\log n)\\) | \\(O(n\log n)\\) | no | in-place, no recursion |
| Counting/radix | \\(O(n+k)\\) | — | yes | integers/keys only |

The \\(O(n\log n)\\) bound is **optimal** for comparison-based sorting (a decision-tree argument). Non-comparison sorts beat it only by exploiting key structure.

## Divide and Conquer

Merge sort and quicksort split the problem, solve the halves, and combine — analyzed with the [Master Theorem](../../math/discrete/recurrences.md): \\(T(n) = 2T(n/2) + O(n) = O(n\log n)\\).

## Example: Binary Search in Rust (runnable)

```rust
fn binary_search(a: &[i32], target: i32) -> Option<usize> {
    let (mut lo, mut hi) = (0usize, a.len());
    while lo < hi {
        let mid = lo + (hi - lo) / 2;
        if a[mid] == target {
            return Some(mid);
        } else if a[mid] < target {
            lo = mid + 1;
        } else {
            hi = mid;
        }
    }
    None
}

fn main() {
    let a = [1, 3, 4, 7, 9, 11, 15];
    println!("{:?}", binary_search(&a, 9));  // Some(4)
    println!("{:?}", binary_search(&a, 6));  // None
}
```

## See Also

- [Data Structures](data-structures.md)
- [Complexity and Analysis](complexity.md)
- [Recurrence Relations](../../math/discrete/recurrences.md)
