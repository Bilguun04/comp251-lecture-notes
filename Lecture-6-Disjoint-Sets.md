The disjoint data structure (also known as Union-Find data structure) is used to manage a collection of disjoint sets. It supports two main operations efficiently.
1. **Find**: Determine which set a particular belongs to.
2. **Union**: Merge two sets into one.
---
- Each set is represented by a root element (also called a representative)
- Elements in the same set share the same root.
- The data structure is typically implemented using trees, where each tree represents a set, and the root of the tree is the representative of the set.
---
**Find:**
- Given an element, find the root of the set it belongs to
- This involves traversing the tree upward until the root is reached.
**Union:**
- Given two elements, merge the sets they belong to.
- This involves making the root of one set point to the root of the other set.
- The depth of a node is the number of edges from the node to the tree’s root node. A root node will have a depth of 0.
- The height of a node is the number of edges on the longest path from the node to a leaf. A leaf node will have a height of 0.
---
**Union - Heuristic - by size**
- Heuristic to control the height to the trees after merging.
- **Idea**: Merge tree with smaller number of nodes into the tree with the largest number of nodes.