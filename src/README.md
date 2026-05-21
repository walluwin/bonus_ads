# Bonus Task – Dijkstra's Algorithm

## Overview

This is a bonus task for the Algorithms and Data Structures course. The goal was to extend the existing graph implementation to support weighted edges and find the shortest path from a starting vertex to all other vertices using Dijkstra's Algorithm.

## Files

- `Graph.java` – contains the `Graph` class with weighted adjacency list and the `dijkstra()` method
- `Main.java` – creates a sample graph and runs the algorithm from vertex 0

## How It Works

The graph uses an adjacency list where each entry stores both the destination vertex and the edge weight. The `dijkstra(int start)` method:

1. Sets all distances to infinity except the starting vertex (set to 0)
2. Picks the unvisited vertex with the smallest current distance
3. Updates distances to its neighbors if a shorter path is found
4. Repeats until all reachable vertices are visited

No priority queue is used — just arrays and simple loops as allowed.

## How to Run

```bash
javac Graph.java Main.java
java Main
```

## Sample Output

```
Shortest distances from vertex 0:
Vertex 0 -> 0
Vertex 1 -> 3
Vertex 2 -> 1
Vertex 3 -> 4
Vertex 4 -> 7
Vertex 5 -> 9
```

## Graph Used for Testing

```
0 --4-- 1
|       |
1  2    1
|       |
2 --5-- 3 --3-- 4 --2-- 5
              |               |
              +-------7-------+
```

Edges:
- 0 → 1 (weight 4)
- 0 → 2 (weight 1)
- 2 → 1 (weight 2)
- 1 → 3 (weight 1)
- 2 → 3 (weight 5)
- 3 → 4 (weight 3)
- 4 → 5 (weight 2)
- 3 → 5 (weight 7)

## Notes

- The graph is undirected and weighted
- Unreachable vertices are printed as "unreachable"
- Time complexity: O(V²) using simple array-based approach
