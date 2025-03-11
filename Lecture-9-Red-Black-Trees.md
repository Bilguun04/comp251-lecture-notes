**Key Properties of Red-Black Trees:**
1. **Node Colour:** Every node is either red or black.
2. **Root Property:** The root is always black.
3. **Leaf Property:** All leaves (null pointers) are always black.
4. **Red Property:** If a node is red, both its children must be black (no two red nodes can be adjacent)
5. **Black Depth Property:** Every path from a node to its descendant leaves must have the same number of black nodes. This ensures the tree is balanced.
---
**Operations in Red-Black Trees:**
1. **Search - O(log n)**
	- Search in a Red-Black Tree is identical to search in a regular BST.
	- Start at the root and traverse left or right based on the comparison with the target value.
2. **Insertion - O(log n)**
	- Insert the new node as in a regular BST and colour it red.
	- If the parent of the new node is black, the tree remains valid.
	- If the parent is red, check the uncle (sibling of the parent):
		- If Uncle is Red: Recolour the parent, uncle, the grandparent.
		- If Uncle is Black or Null: Perform rotation and recolouring based on the position of the new node.
3. **Deletion - O(log n)**
	- Delete the node as in regular BST.
	- If the deleted node was black, the tree may violate the Red-Black properties.
	- Fix the tree by performing rotations and recolouring based on the sibling of the deleted node.

**You should use left or right rotations for rotation red-black trees!**

---
**AVL vs Red-Black Trees**
- AVL trees are more strictly balanced, which means it is faster in searching.
- Red-Black Trees have less constraints and insert/remove operations require less rotations, which means it is faster when inserting or removing node.
- AVL trees store balanced factors or heights with each node.
- Red-Black Tree requires only one bit of information per node.