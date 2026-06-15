# Graph Algorithms

Graph algorithms operate on the vertices-and-edges structures of [Graph Theory](../../math/discrete/graph-theory.md). They solve routing, scheduling, network, and planning problems — including robot [motion planning](../../app/robotics/planning.md).

## Traversal

- **Breadth-first search (BFS)** — explores by distance; finds shortest paths in **unweighted** graphs. \\(O(V+E)\\).
- **Depth-first search (DFS)** — explores deep first; basis of topological sort, cycle detection, and connectivity. \\(O(V+E)\\).

## Shortest Paths

| Algorithm | Handles | Complexity |
|---|---|---|
| BFS | unweighted | \\(O(V+E)\\) |
| Dijkstra | non-negative weights | \\(O((V+E)\log V)\\) with a heap |
| Bellman–Ford | negative weights, detects neg. cycles | \\(O(VE)\\) |
| A\\(^*\\) | heuristic-guided | best-case far below Dijkstra |
| Floyd–Warshall | all pairs | \\(O(V^3)\\) |

**Dijkstra** greedily expands the closest unvisited vertex using a priority queue (min-heap). **A\\(^*\\)** adds an admissible heuristic \\(h(n)\\) to focus the search toward the goal — the standard in robotics and games.

## Minimum Spanning Tree

Connect all vertices with minimum total edge weight:
- **Kruskal** — sort edges, add if they don't form a cycle (uses union-find). \\(O(E\log E)\\).
- **Prim** — grow a tree from a start vertex with a heap. \\(O(E\log V)\\).

Used in network design, clustering, and circuit layout.

## Other Important Problems

- **Topological sort** — order a DAG respecting dependencies (build systems, scheduling).
- **Max flow / min cut** (Ford–Fulkerson, Edmonds–Karp) — networks, matching, image segmentation.
- **Connected components / strongly connected components** — clustering and reachability.

## Dijkstra in Pseudocode

```text
dist[source] = 0; push (0, source) to min-heap
while heap not empty:
    (d, u) = pop min
    if d > dist[u]: continue
    for each edge (u, v, w):
        if dist[u] + w < dist[v]:
            dist[v] = dist[u] + w
            push (dist[v], v)
```

## See Also

- [Graph Theory](../../math/discrete/graph-theory.md)
- [Motion Planning](../../app/robotics/planning.md)
- [Data Structures](data-structures.md) — heaps and union-find.
