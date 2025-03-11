A heap is a specialized tree-based data structure that satisfies the heap property:
- In a min-heap, the value of each node is greater than or equal to the value of its parent, with the smallest value at the root.
- In a max-heap, the value of each node is less than or equal to the value of its parent, with the largest value at the root.
---
**Key Features**
- Complete Binary Tree: All levels are fully filled except possible the last level, which is filled from left to right.
- Heap Property: The value of each node satisfies the heap condition.
---
**Operations**
1. **Insert - O(log n)**
	- Add a new element to the heap.
	- Place it at the next available position and perform a heapify-up operation to maintain the heap property.
2. **Extract Min/Max - O(log n)**
	- Remove and return the root element
	- Replace the root with the last element and perform a heapify-down operation to maintain the heap property.
3. **Peek - O(1)**
	- Return the root element without removing it.
4. **Heapify - O(n)**
	- Convert an arbitrary array into a heap.
---
- **Disjoint Sets:** Used for managing and merging sets efficiently, with applications in graph algorithms and clustering.
- **Heap:** Used for managing priority-based data, with applications in sorting, shortest path algorithms, and priority queues.
---
**Heap Sort**
- Combines the better attributes of merge sort and insertion sort.
	- Like merge sort, worst case running time is O(n log n)
	- Like insertion sort, sorts in place.
- Introduces an algorithm design technique
	- Create data structure (heap) to manage information during the execution of an algorithm.
- The heap has other applications beside sorting.