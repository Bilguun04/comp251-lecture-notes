**Definition:**
- An abstract way of representing connectivity using nodes and edges.
- Nodes and edges can have some auxiliary information. For example, vertex represents homes or buildings in a town. On the other hand, edge represents the roads and routes between them.
- **Path:** Sequence of adjacent vertices.
- **Simple Path:** Path such that all its vertices are distinct.
- **Cycle:** Path that starts and ends at the  same vertex.
- **Simply Cycle:** Cycle where each vertex is distinct.
---
**Adjacency List** is collection of unordered lists used to represent a finite graph. Each unordered list within an adjacency list describes the set of neighbours of a particular vertex in the graph.
**Tree:** We say that an undirected graph is a tree if it is connected and does not contain a cycle. Rooted trees are fundamental objects in computer science, because they encode the notion of a hierarchy. Many websites are organized according to a tree-like structure, to facilitate navigation. A typical computer science department’s Web site will have an entry page as the root; the People’s page is a child of this entry page.

---
**Breadth-First-Search:**
It is a fundamental algorithm used for traversing or searching tree or graph data structures. It explores all the nodes at the present depth level before moving on to nodes at the next depth level. It also can be described as Brute-Force approach as it goes through every nodes in the graph (worst case).
- **Key Concept:**
	1. **Queue Data Structure:** BFS uses a queue to keep track of the nodes to be explores. The queue follows the First-In-First-Out principle.
	2. **Visited Nodes:** To avoid reprocessing nodes, BFS marks nodes as visited once they are explored.
- **Steps of BFS:**
	1. **Start at the Initial Node:** Begin with a selected node (often called root or source node)
	2. **Enqueue the Initial Node:** Add the initial node to the queue and mark it as visited.
	3. **Explore Nodes Level by Level:** 
		- Dequeue a node from the queue
		- Process the node
		- Enqueue all its unvisited neighbours and mark them as visited.
	4. **Repeat Until the Queue is Empty:** Continue the process until the queue is empty meaning all reachable nodes have been explored.

**Pseudocode:**
```
BFS(graph, start_node):
	queue = Queue()
	visited = set()
	queue.enqueue(start_node)
	visited.add(start_node)

	while queue is not empty:
		current_node = queueu.dequeue()
		process(current_node)

		for neighbor in graph[current_node]:
			if neighbor not in visited:
				queue.enqueue(neighbor)
				visited.add(neighbor)
```

**Applications of BFS:**
1. **Shortest Path in Unweighted Graph:** BFS guarantees the shortest path in terms of the number of edges.
2. **Connected Component:** BFS can be used to find all nodes connected to a given node.
3. **Web Crawlers:** BFS is used to explore web pages level by level.
4. **Social Networking:** BFS can find the shortest path or degrees of separation between users.

**Time Complexity:** $$O(V + E)$$ where V is the number of vertices and E is the number of edges in the graph. This is because each node and edge is processed once.

---
**Depth-First-Search:**
- Explore edges out of the most recently discovered vertex v.
- When all edges of v have been explored, backtrack to explore other edges leaving the vertex from which v was discovered.
- “Search as deep as possible first”
- Continue until all vertices reachable from the original source are discovered.
- If any undiscovered vertices remain, then one of them is chosen as a new source is repeated from that source.

**How DFS works?**
1. Start at a node.
2. Move deeper by visiting an adjacent unvisited node.
3. If no unvisited adjacent nodes exist, backtrack to the previous node.
4. Repeat until all nodes are visited.
---
**DFS Algorithm**
```python
def DFS(node, visited):
	if node is not visited:
		visited.add(node)
		for neighbor in node.neighbors:
			DFS(neighbor, visited)
```
---
**Key Characteristics:**
- Uses a Stack.
- Memory Efficient for deep graphs.
- Does not guarantee shortest path (unlike BFS)
- Applications:
	- Solving mazes
	- Topological sorting
	- Finding strongly connected components
	- Pathfinding in games.