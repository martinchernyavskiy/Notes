## Closest Pair of Points in the Plane
?
- Out of all points in the plane finds the pair that has the shortest distance between them
- Input: p_i = (x_i, y_i) in R2 for i in \[n]
	- n points in R2 space
- Output: delta = min{d(p_i, p_j): i,j in \[n] with i !=j}
				where d is a regular euclidean distance
- Basic approach:
	- If x coordinate for each point is zero, we can then sort the points by their y values using merge sort and then compare each consecutive pair. This runs in O(nlogn) time
- D&C approach
	- Split points evenly in L and R based on if point is to the left or to the right of the other
	- 