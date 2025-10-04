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
	- Recursively solve each side to get the pairs with shortest distances between each other. The main delta is then at most the minimum of these distances, given there might be a pair closer to each other but from different sides
		- If we had to check every pair, this would take O(n^2), thus we only consider points that lie within delta star distance from the boundary (that is the minimum of the 2 deltas calculated from recursion)
			- But if all points fall within that distance, still O(n^2), but we want linear time
### Checking Crossing Pairs in Middle Strip
- Bounds for fixed p (x.y) in intersection of M and L
![[Pasted image 20251004171453.png]]
