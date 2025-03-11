- It is a problem solving paradigm where we try to make a problem simpler by dividing it into smaller parts and conquering them.
- Recursive in structure:
	- **Divide** the problem into sub-problems that are similar to the original but smaller in size.
	- **Conquer** the sub problems by solving them recursively. If they are small enough, just solve them in a straightforward manner.
	- **Combine** the solutions to create a solution to the original problem.
---
**Merge Sort**
``` python
def mergeSort(arr):
	if len(arr) > 1:
		mid = len(arr) // 2
		left = arr[:mid]
		right = arr[mid:]
		mergeSort(left)
		mergeSort(right)

		merge(arr, left, right)

def merge(arr, left, right):
	i = j = k = 0

	while i < len(left) and j < len(right):
		if left[i] < right[j]:
			arr[k] = left[i]
			i += 1
		else:
			arr[k] = right[j]
			j += 1
		k += 1

	while i < len(left):
		arr[k] = left[i]
		i += 1
		k += 1

	while j < len(right):
		arr[k] = right[j]
		j += 1
		k += 1
```
---
**Solving Recurrences**
- **Substitution method:** We guess a bound and then use mathematical induction to prove that our guess is correct.
- **Recursion-tree method:** Converts the recurrence into a tree whose nodes represent the costs incurred at various levels of the recursion. We use techniques for bounding summations to solve the recurrence.
- **Master Theorem method:** This is the most commonly used way to solve recurrence. The master theorem is a quick way to solve recurrence of the form: $$T(n)=a*T(n/b)+f(n)$$ Where:
	- a>=1, number of subproblems
	- b>1, factor by which the problem size is reduced
	- f(n), cost of dividing and combining