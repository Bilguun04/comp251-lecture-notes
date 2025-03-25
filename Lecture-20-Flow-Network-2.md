**Min-Cut**
A min-cut in flow network is the smallest set of edges whose removal disconnects the source from the sink while minimizing the total capacity of the removed edges. It is directly related to the max-flow in the network via the max-flow min-cut theorem.

**Key-Concepts:**
1. **Definition:**
	- Cut: A partition of the graph’s nodes into two disjoint sets.
	- Capacity of a Cut: Sum of capacities of edges going from S to T.
	- Min-Cut: The cut with the smallest capacity that still disconnects s and t.
2. **Max-flow Min-cut theorem:** The maximum flow from s to t in a flow network is equal to the capacity of the min-cut.

**How to find Min-Cut?**
1. Compute the Max-Flow (using For-Fulkerson) to saturate the network.
2. Identify reachable nodes from s in residual graph. After computing max-flow, constructs the residual graph and then perform BFS/DFS from s to find all nodes still reachable.
3. Extract the min-cost edges. The edges from S to T in the original graph from the min-cut.

**Applications of Min-Cut:**
1. **Network Reliability:** Finding weak points in computer/transportation networks.
2. **Image Segmentation:** Separating foreground/background in computer vision.
3. **Community Detection:** Splitting social networks into clusters.
4. **Scheduling Problems:** Assigning tasks to machines while minimizing bottlenecks.