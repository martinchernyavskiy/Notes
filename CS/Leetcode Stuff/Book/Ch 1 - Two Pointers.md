## Two Pointers
- Pointer: variable representing index within a data structure
- Using second pointer allow to make *comparisons*
- 2 nested for-loops O(n^2)
```Python
for i in range(n):
	for j in range(i+1, n):
		compare(nums[i], nums[j])
```
- *Predictable Dynamics*: for example in a sorted array, we can predict whether the value that pointer moves to is greater or smaller

## Two-pointer Strategies
- 