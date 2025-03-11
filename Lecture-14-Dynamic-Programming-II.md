The knapsack problem is a classic optimization problem in computer science and mathematics. It is often solved using dynamic programming to achieve an efficient solution. For example, you’ll have n set of items, each with a weight w_i, and a value v_i. A knapsack with a maximum weight capacity W. The goal is to determine the maximum value of items that can be placed into the knapsack without exceeding its weight capacity. These are types of Knapsack Problems:
1. **0/1 Knapsack Problem:**
	- Each item can either be included (1) or excluded (0) from the knapsack
	- No fractional items are allowed.
2. **Fractional Knapsack Problem:**
	- Items can be divided into fractions, and you can take a fraction of an item.
	- This problem is typically solved using a greedy algorithm.
3. **Unbounded Knapsack Problem:**
	- Each item can be included multiple times. (no limit on the number of copies)
---
**Dynamic Programming Approach for 0/1 Knapsack:**
Steps:
1. **Define the DP Table:**
	- Create a 2D table ``dp`` where ``dp[i][j]`` represents the maximum value achievable using the first ``i`` items and a knapsack capacity of ``j``.
2. **Initialize the Table:**
	- ``dp[0][j]=0`` for all ``j`` (no items, so value is 0).
	- ``dp[i][0]=0`` for all ``i`` (zero capacity, so value is 0).
3. **Fill the Table:**
	- For each ``i`` and each possible weight ``j``:
		- If the item’s weight w_i is less than or equal to j:
			- ``dp[i][j]=max(dp[i-1][j], v_i+dp[i-1][j-w_i])`` 
			- ``dp[i-1][j]``: Exclude the item.
			- ``v_i+dp[i-1][i-w_i]``: Include the item.
		- Else: $$dp[i][j]=dp[i-1][j]$$
		- The item cannot be included because its weight exceeds the capacity.
4. **Result**
	- The value ``dp[n][W]`` gives the maximum value achievable with n items and capacity W.