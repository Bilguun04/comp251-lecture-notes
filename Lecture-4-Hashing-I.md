**The loop invariant is inductive**
- Base Case: when the algorithm begins, lo = 0 and hi = len(A) - 1. Lo and hi encloses ALL values so target must be between lo and hi.
- Inductive hypothesis: suppose at any iteration of the loop, lo and hi still encloses the target value.
- Inductive step:
	- Case 1: ``If A[mid] > target``, then the target must be between lo and mid.
	- Case 2: ``If A[mid] < target``, then the target must be between mid and hi
	- In either case, we preserve the inductive hypothesis for the next loop.
---
**Proof Correctness**
- Notice for each iteration, lo always increases and hi always decreases. These value will converge at a single location where lo = hi.
- By the induction hypothesis, ``A[lo] <= target <= A[hi]``.
---
**Loop Invariance**
We must show three things about a loop invariant:
1. Initialization: It is true prior to the first iteration of the loop.
2. Maintenance: If it is true before an iteration of the loop, it remains true before the next iteration.
3. Termination: When the loop terminates, the invariant gives us a useful property that helps show that the algorithm is correct.
---
Using loop invariants is like mathematical induction.
- You prove a base case and an inductive step.
- Showing that the invariant holds before the first iteration is like the base case.
- Showing that the invariant holds from classical mathematical induction. Here, we stop the “induction” when the loop terminates instead of using it infinitely.
We can show the three parts in any order.
---
**Running time - Primitive Operations**
- Simple computer operation that can be performed in time that is always the same, independent of the size of the bigger problem solved.
	- Assigning a value to a variable: x -> 1
	- Calling a method: Expos.addWin()
		- Note: does not include the time to execute the method
	- Returning from a method: return x
	- Arithmetic operations on primitive types
	- Comparisons on primitive types: x == y
	- Conditionals: ``if(…) then … else …
	- Indexing into an array: ``A[i]``
	- Following object reference: Expos.losses
- Note: Multiplying two large integers is not a primitive operation, because the running time depends on the size of the numbers multiplied.
---
**What does O(1) mean?**
- We say t(n) is O(1), if there exist two positive constants n0 and c such that, for all n >= n0. So, it means that t(n) is bounded.
---
**The difference between big omega and big O notation is that big O notation is the upper bound of the graph (worst case scenario), and big omega is the lower bound of the graph (best case scenario)**

---
**Hashing**
- A map is a set of (key, value) pairs. Each key maps to at most one value.
- Real world hashing examples includes:
	1. Compilers: a compiler that translates a programming language maintains a symbol table, in which the keys of elements are arbitrary character strings corresponding to identifiers in the language.
	2. Password Authentication: keys are usernames, and values are passwords (hash(passwords))
	3. Data Consistency: for example, after downloading a file, you can compare the fingerprint of the downloaded file with the fingerprint of the original file. If the two fingerprints differ, the files are surely different, if they are the same, the files are equal with a very high probability.
---
**Why hashing is so important**
- Hashing is an extremely effective and practical tehcnique.
- Many applications require a dynamic set that supports only the dictionary operations.
	- INSERT, SEARCH, DELETE
	- A hash table is an effective data structure for implementing dictionaries.
		- Under reasonable assumptions, the average time to search for an element in a hash table is O(1).
- A hash table generalizes the simpler notion of an ordinary array.
	- Directly addressing into an ordinary array make effective use of our ability to examine an arbitrary position in an array in O(1) time.
		- The array index is computed from the key.
		- To allocate an array that has one position for every possible key.
---
**Hash map**
- Has map (hashing function + hash table)
	- Direct addressing: an element with key k is stored in slot k.
	- Hash Function: an element with key k is stored in slot h(k).
---
**Hash table**
- The hash function reduces the range of array indices. Instead of a size of |U|, the array can have size m.
- The catch: We reduce the storage requirement while we maintain the benefit of searching in O(1).
	- This boundary is for the average-case time, whereas for direct addressing it holds for the worst-case time.
- The hitch: Two keys may hash to the same slot (in other words, collision)
---
**Hashing - Function**
- A good hash function:
	- Satisfies the condition of simple uniform hashing.
		- Each key is equally likely to any of the m slots.
	- Nearby/similar keys in U should map to different values.
	- Independent of any patterns of U.
	- Can be computed quickly O(1)