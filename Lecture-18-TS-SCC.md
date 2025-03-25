TS stands for Topological Sort.
SCC stands for Strong Connected Components.

**Theorem:** In DFS of a connected undirected graph, we get only tree and back edges. No forward or cross edges.

---
**Directed Acyclic Graph:**
- It is a directed graph with no cycles.
- Directed acyclic graphs can be used to encode precedence relations or dependencies in natural way.
	- **Source:** Any vertex in a DAG that has no incoming edges.
	- **Sink:** Any vertex with no outgoing edges.
	- **Every DAG has at least one source and on sink,** but may have more than one of each.

**Key Properties of DAG:**
1. **Topological Ordering Possible:** Nodes can be linearly ordered such that for every directed edge, u comes before v in the ordering.
2. **No self-loops:** A node cannot have an edge pointing to itself.
3. **Dynamic Programming Friendly:** Many problems on DAGs can be solved efficiently using DP due to their acyclic nature.
---
**Topological Sort** is an ordering of the vertices of a directed  acyclic graph (DAG) such that for every directed edge u -> v, vertex u before v in the ordering. It essentially arranges nodes in a linear sequence where all dependencies are respected.

**Key Properties of Topological Sort:**
1. **Only applicable to DAGs:** If the graph has a cycle, topological sort is impossible
2. **Not Unique:** A DAG can have multiple valid topological orderings.
3. **Dependency Resolution:** Used in scheduling tasks, building systems, course prerequisites, and event sequencing.
---
**Strongly Connected Components**
SCC in a directed graph is a maximal subgraph where every pair of nodes is mutually reachable. SCCs decompose a directed graph into disjoint subgraphs that are internally strongly connected but not connected to each other in the same way.

**Key Properties:**
1. **Maximally:** No larger subgraph contains the SCC and remains strongly connected.
2. **Mutual Reachability:** For any two nodes u and v in an SCC, both u->v and v->u paths exist.
3. **Acyclic Component Graph:** If each SCC is contracted to a single node, the resulting graph is a DAG.

**Applications:**
1. **Compiler Optimization:** Detecting loops in control flow graphs.
2. **Social Networking:** Identifying tightly-knit communities.
3. **Vulnerability Analysis:** Finding critical nodes in networks.
4. **Route Planning:** Ensuring connectivity in transportation networks.

**Why SCC matters?**
- **Cycle Detection:** All nodes in SCC lie in a common cycle.
- **DAG Simplification:** SCCs condense a graph into a DAG for easier analysis.
- **Network Robustness:** SCCs reveal critical nodes whose removal disconnects the graph.