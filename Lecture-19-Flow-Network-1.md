Flow network is a directed graph where each edge has a capacity (maximum flow it can carry) and a flow (actual passing through). It is used to model systems where a resource moves from a source to a sink while respecting capacity constraints.
**Key Components:**
1. Directed Graph
2. Source
3. Sink
4. Capacity
5. Flow
6. Flow Conservation

**Key Concepts:**
1. **Residual Network:** A graph showing remaining capacity. Used in algorithms like **Ford-Fulkerson** to find augmenting paths.
2. **Augmenting Path:** A path from s to t in the residual network where flow can be increased.
3. **Max-Flow Min-Cut Theorem:** The maximum flow equals the minimum capacity of edges to disconnect s from t.
---
**Algorithms to find maximum flow**
1. **Ford-Fulkerson Algorithm** is a greedy algorithm, and uses augmenting paths in residual network. Time Complexity is O(E x max_flow).
```python
def ford_fulkerson(graph, source, sink):
	max_flow = 0
	residual = copy(graph)
	path = bfs(residual, source, sink)
	while path:
		flow = min(residual[u][v] for (u, v) in path)
		for u, v in path:
			residual[u][v] -= flow
			residual[v][u] += flow
		max_flow += flow
		path = bfs(residual, source, sink)
	return max_flow
```
2. **Edmond-Karp Algorithm** is an optimized Ford-Fulkerson algorithm using breadth first search.
3. **Dinic’s Algorithm** uses BFS layers + DFS blocking flows.
4. **Naive Algorithm:**
	- It is the simplest, most straightforward approach to solving a problem, often designed without optimization or advanced techniques. It typically has high/space complexity but is easy to understand and implement. Naive algorithm is useful for teaching fundamental concepts, serving as a baseline for comparing optimized solutions and solving small-scale problem where efficiency is not critical.
	- **Characteristics:** 
		- Brute-Force approach: It examines all possible solutions exhaustively
		- No-advanced optimization: Avoids complex data structure (such as hash tables) or mathematical insights.
		- Clear but inefficient.
---
**Applications**
1. **Transportation Networks:** Maximizing goods shipped from factories to markets.
2. **Computer Networks:** Data packet routing with bandwidth limits.
3. **Bipartite Matching:** Matching jobs to applicants (modelled as a flow network)
4. **Image Segmentation:** Separating foreground/background in computer vision.