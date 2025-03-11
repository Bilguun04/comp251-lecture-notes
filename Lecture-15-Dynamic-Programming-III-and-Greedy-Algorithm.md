**Greedy - Activity Selection Problem**
Lets say there is an input that represents s_i (start time of activity i), f_i (finish time of activity i), and we need to return subset A of maximum number of compatible activities.
**Intuition:**
- We should choose an activity that leaves the resource available for as many other activities as possible.
- Of the activities we end up choosing, one of them must be the first one to finish.
- Choose the activity in S with the earliest finish time.
---
Let’s start by recognizing **key characteristics of greedy algorithm:**
1. **Greedy Choice Property:** At each step, the algorithm makes the choice that seems best at the moment, without considering future consequences.
2. **Optimal Substructure:** The problem can be broken down into smaller subproblems, and the optimal solution to the problem can be constructed from the optimal solutions of the subproblems.
3. **Irrevocable Decisions:** Once a choice is made, it cannot be changed later.
---
**Steps to design greedy algorithm:**
1. **Define the Problem:** Clearly state the problem and the objective. (For example, maximizing profit or minimizing cost)
2. **Identify the Greedy Choice:** Determine the criterion for making the greedy choice at each step. (select the item with the highest value-to-weight ratio).
3. **Prove the Greedy Choice Property:** Show that the greedy choice leads to an optimal solution.
4. **Prove the Optimal Substructure:** Demonstrate that the problem can be solved by combining the greedy choice with the optimal solution to the remaining subproblem.
5. **Implement the Algorithm:** Write the algorithm to make the greedy choices iteratively or recursively.
---
**Advantages of Greedy Algorithms:**
1. **Efficiency:** Greedy algorithm are often simple and fast, with time complexities like O(n log n) or O(n).
2. **Intuitive:** The greedy approach is easy to understand and implement.
3. **Optimal for Some Problems:** For problems like the Fractional Knapsack and Activity Selection, greedy algorithms provide optimal solutions.

**Disadvantages of Greedy Algorithms:**
1. **Not always Optimal:** Greedy algorithms do not always guarantee the globally optimal solution.
2. **Proof of Correctness:** Proving that a greedy algorithm works for a specific problem can be challenging.