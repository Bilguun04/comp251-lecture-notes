DP (Dynamic Programming) breaks a problem into smaller overlapping sub-problems and avoids the computation of the same results more than once. DP looks through all possible sub-problems and never re-computes the solution to any sub-problem. This implies correctness and efficiency, which we can not say of most techniques. This alone makes DP special.

---
**Steps for solving DP Problems:**
1. Define subproblems
2. Write down the recurrence that relates subproblems.
3. Recognize and solve the base cases.
4. Implement a solving methodology.
---
**Top-Down vs Bottom-Up**

Pros:

| Top-Down                                                              | Bottom-Up                                                                               |
| --------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| It is a natural transformation form normal complete search recursion. | Faster if many sub-problems are revisited as there is no overhead from recursive calls. |
| Compute sub-problems only when necessary                              | Can save memory space with DP “on-the-fly” technique.                                   |
Cons:

| Top-Down                                                                                   | Bottom-Up                                                                             |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| Slower if many sub-problems are revisited due to recursive call overhead.                  | For some programmers who are inclined with recursion, this may be not intuitive.      |
| If there are M states, it can use up to O(M) table size which can lead to memory problems. | If there are M states, bottom-up DP visits and fills the value of all these M states. |

---
**Main Idea of Dynamic Programming**: Solve the sub-problems in an order that makes sure when you need an answer, it’s already been computed.