BST - Binary Search Trees
AVL - Adelson-Valesky and Landis

---
**Binary Search Tree**
- All elements in the left subtree are less than the node’s value.
- All elements in the right subtree are greater than the node’s value.
- Both the left and right subtrees must also be binary search trees.

**Operations:**
- Search(T, k): O(h)
	- Start at the root.
	- If the target value is equal to the current node’s value, return the node.
	- If the target value is less than the current node’s value, move to the left subtree.
	- If the target value is greater than the current node’s value, move to the right subtree.
	- Repeat until the value is found or a null pointer is reached.
- Insert(T, k): O(h)
	- Start at the root
	- If the tree is empty, create a new node and make it the root.
	- Otherwise, compare the value to be inserted with the current node’s value.
		- If it is less, move to the left subtree.
		- If it is greater, move to the right subtree.
	- Repeat until an empty spot is found, then insert the new node there.
- Delete(T, k) : O(h)
	- Deleting a node from a BST has three cases: which are when node has not children, when node has only one child and node has two children.
		- When node has no children, simply remove the node.
		- When node has only one child, replace the node with its child.
		- When node has two children, find the in-order-successor (smallest node in the right subtree) or the in-order predecessor (largest node in the left subtree) and replace the node’s value with the successor’s value, and lastly delete the successor node.
---
**Advantages of BST:**
1. **Efficient Search:** Average time complexity of O(log n) for search, insertion, and deletion.
2. **Dynamic Size:** Can grow and shrink dynamically.
3. **Sorted Order:** Maintains elements in sorted order, making it useful for range queries and in-order traversal

**Disadvantages of BST:**
1. **Balancing required:** Performance degrades to O(n) if the tree becomes unbalanced.
2. **No random access:** Cannot access elements by index like in arrays.
---
**Balanced BSTs**
1. **AVL Tree:** Maintains balance by ensuring the heights of the left and right subtrees differ by at most 1.
2. **Red-Black Tree:** Uses colour coding and rotation rules to maintain balance.
3. **B-Tree:** Used in database and file systems for efficient disk access.
---
**AVL Tree**
In regular binary search tree, operations like insertion and deletion can lead to an unbalanced tree, where the tree becomes skewed. In such cases, the time complexity of operations degrades to O(n). AVL trees prevent this by automatically rebalancing themselves after every insertion or deletion.

**Rotations in AVL Trees:**
To maintain balance, AVL trees use rotations. There are four types of rotations.
	1. **Left Rotation (LL Rotation):** Used when the right subtree is heavier.
	2.  **Right Rotation (RR Rotation):** Used when the left subtree is heavier.
	3. **Left-Right Rotation (LR Rotation):** Used when the left subtree is heavier, and the right child of the left subtree is heavier.
	4. **Right-Left Rotation (RL Rotation):** Used when the right subtree is heavier, and the left child of the right subtree is heavier.

**Insertion in AVL Trees - O(log n):**
1. Perform a standard BST insertion.
2. Update the heights of the nodes along the insertion path.
3. Check the balance factor of each node.
4. If the balance factor violates the AVL property, perform the appropriate rotation to rebalance the tree.

**Deletion in AVL Trees - O(log n):**
1. Perform a standard BST deletion.
2. Update the heights of the nodes along the deletion path.
3. Check the balance factor of each node.
4. If the balance factor violates the AVL property, perform the appropriate rotation to rebalance the tree.
****