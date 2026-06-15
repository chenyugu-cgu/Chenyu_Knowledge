# Graph Theory

A **graph** \\(G = (V, E)\\) is a set of vertices \\(V\\) connected by edges \\(E\\). Graphs model networks of every kind — circuits, roads, molecules, the web, robot configuration spaces.

## Vocabulary

- **Directed vs. undirected** — edges have a direction or not.
- **Weighted** — edges carry costs/distances.
- **Degree** — number of edges at a vertex.
- **Path, cycle, connected, tree** — a tree is a connected acyclic graph with \\(|V|-1\\) edges.
- **Complete, bipartite, planar** — structural families.

## Representations

- **Adjacency matrix** \\(A\\) — \\(A_{ij}=1\\) if edge \\((i,j)\\) exists; \\(O(V^2)\\) space, fast edge lookup.
- **Adjacency list** — per-vertex neighbor lists; \\(O(V+E)\\) space, efficient for sparse graphs.

Powers of \\(A\\) count walks: \\((A^k)_{ij}\\) is the number of length-\\(k\\) walks from \\(i\\) to \\(j\\).

## Traversal

- **Breadth-first search (BFS)** — explores level by level; finds shortest paths in unweighted graphs.
- **Depth-first search (DFS)** — explores deep first; underlies topological sort, cycle detection, connectivity.

Both run in \\(O(V + E)\\).

## Classic Problems

| Problem | Algorithm |
|---|---|
| Shortest path (nonneg. weights) | Dijkstra |
| Shortest path (neg. weights) | Bellman–Ford |
| All-pairs shortest paths | Floyd–Warshall |
| Minimum spanning tree | Kruskal, Prim |
| Maximum flow | Ford–Fulkerson |
| Topological order | DFS / Kahn |

These are developed in [Graph Algorithms](../../cs/algorithms/graph-algorithms.md).

## Special Structures

- **Euler path** — uses every edge once (exists iff ≤2 odd-degree vertices) — the Königsberg bridges.
- **Hamiltonian path** — visits every vertex once (NP-hard).
- **Graph coloring** — assign colors so adjacent vertices differ; models scheduling and register allocation.

## Applications

Robot [path planning](../../app/robotics/planning.md), circuit analysis ([Circuit Laws](../../eng/electrical/circuits.md)), social/biological networks, dependency resolution, and routing.

## See Also

- [Graph Algorithms](../../cs/algorithms/graph-algorithms.md)
- [Motion Planning](../../app/robotics/planning.md)
- [Data Structures](../../cs/algorithms/data-structures.md)
