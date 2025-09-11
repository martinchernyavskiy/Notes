## Definitions
- *Pointer*: variable representing index within a data structure
- Using second pointer allow to make *comparisons*
- 2 nested for-loops O(n^2)
```Python
for i in range(n):
	for j in range(i+1, n):
		compare(nums[i], nums[j])
```
- *Predictable Dynamics*: for example in a sorted array, we can predict whether the value that pointer moves to is greater or smaller

## Two-pointer Strategies
?
- Usually take O(n) time by not using nested for-loops
- *Inward Traversal*
	- Pointers start at opposite ends and moving towards each other
	- Adjust positions based on comparisons
	- Or, meet/cross each other
	- *Ideal for when we need to compare elements from different ends of data structure*
- *Unidirectional Traversal*
	- Pointers start at the same end of data structure (beginning)
	- Use right to find information and left to keep track of information
- *Staged Traversal*
	- Traverse with one pointer until it lands on element meeting condition
		- Then traverse with second pointer
	- First pointer used for search, second pointer finds additional information about first

## When to use?
- Usually requires a linear data structure (array, linked list).
- "Sorted array" indicates that a problem can be solved using two-pointer algorithm
- 