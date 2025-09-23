
## 9/23

#### General Notes
- Paradigm
	- Recursive
		- Number of distinct subproblems in recursion tree remains slow
		- Each solved only once
- Memoization
	- Keep track of computed solutions
	- Top-down
	- Generic
- Iteration
	- Bottom-up
	- Build upp table of solved instances from easier to harder
	- Ad hoc process
- 

### Fibonacci
?
- Trivial 
	- Depth of n, 2^n normally
	- Recursion tree, recurrence for number of additions A(n)
	- Golden ration to the n
- Use memoization, reserve array
	- Complexity O(n)
	- O(n^2) for bit complexity and space complexity
	- Iterative approach allows for O(1) space complexity since we only need to know previous 2 values in the table
	- Bit complexity time O(n^2), space O(n)

### Weighted Interval Scheduling (Agenda Problem)
?
- Objective is to maximize the total value from the events, can'r select overlapping events
- Think of a number line with events being segments from respective numbers on the number line
	- Each line has a value
- Want to find a subset of non overlapping intervals to maximize value
.
- Input: Intervals with real number entries 
- Output: Subset S of indices of 1 through n such that no intervals I_i and I_j that are in S overlap and the value

## 9/25

### Knapsack
?
- 

### Longest Increasing Subsequence
?
- 