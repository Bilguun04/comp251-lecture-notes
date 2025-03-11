When hashing a lot of values into the hash table, it is very common that collision occur. There are two main methods for fixing collision.

---
**Collision**: When two keys hash to the same slot in the memory.

---
**Chaining:**
- When inserting keys into slots, we’ll have multiple keys that goes into same slot. Then we just make the slot linked list and insert it into the slot. Each index in the hash table contains a pointer to the head of a linked list. All keys that hash to the same index are added to this list.
- Steps in chaining:
	1. Insertion: Computer hash value of the key to determine the index. If the index is empty, create a new linked list and store the key-value pair. If the index is not empty, append the key-value pair to the linked list at that index.
	2. Search: Computer the has value of the key to determine the index. Traverse the linked list at that index to find the key. If the key is found, return the associated value. Otherwise, return “not found”
	3. Deletion: Compute the has value of the key to determine the index. Traverse the linked list at that index to find the key. If the key is found, remove the node from the linked list.
- Example:
	- Consider hash table of size 5 and a simple has function: hash(key) = key%5
	- Insert keys: 10, 15, 20, 25, 30
	- Hash values are all zeroes. (because all of them are multiplications of 5)
	- The hash table will look like this:
		- Index 0: 10 -> 15 -> 20 -> 25 -> 30
		- Index 1: Empty
		- Index 2: Empty
		- Index 3: Empty
		- Index 4: Empty
- Advantages of Chaining:
	1. Handles Collisions Gracefully: Multiple keys can hash to the same index without any issues.
	2. Dynamic size: The linked list can grow as needed, unlike open addressing, which has fixed size.
	3. Simple Implementation: Easy to implement and understand
- Disadvantages of Chaining:
	1. Memory Overhead: Requires extra memory for storing pointers in the linked list.
	2. Worst-Case Performance: If all keys hash to the same index, the linked list becomes long, leading to O(n) time complexity for search, insertion, and deletion
	3. Cache Inefficiency: Linked lists are not cache-friendly compared to arrays.
---
**Open Addressing:**
- The difference between chaining and open addressing is that open addressing resolves collision by finding alternate empty slot within the hash table itself. This means that all elements are stored directly in the hash table, and no additional data structure (like linked lists) are used.
- How open addressing works:
	1. Hash function: A hash function is used to map keys to indices in the hash table.
	2. Collision handling: If a collision occur the algorithm probes (searches) for the next available empty slot in the hash table using a predefined probing sequence.
	3. Storage: Each key-value pair is stored directly in the hash table array.
- Probing Techniques:
	1. Linear Probing: If the computed index is occupied, the algorithm checks the next slot sequentially
	2. Quadratic Probing: If the computed index is occupied, the algorithm checks slots at quadratic intervals
	3. Double Hashing: Uses a second hash function to determine the step size for probing.
- Steps in Open Addressing:
	1. Insertion: Compute the hash value of the key to determine the initial index. If the slot is empty, insert the key-value pair. If the slot is occupied, use the probing sequence to find the next available slot and insert the pair there.
	2. Search: Compute the has value of the key to determine the initial index. If the key at that index matches, return the value. If the slot is empty, the key is not in the table. If the slot is occupied but the key does not match, use the probing sequence to check the next slots until the key is found of an empty slot encountered.
	3. Deletion: Deleting an element in open addressing requires special care because simply removing the key-value pair break the probing sequence for other keys.