## Paradigm
?
- Break up instance into considerably smaller ones
- Recursively solve these
- Combine their solutions into one for a given instance

## Sorting
?
- Input: array A\[1...n] of integers with n >= 1
- Output: Sort(A), A sorted in non-decreasing order
### Merge Sort
- Include brief description of the algorithm, may use pictures also
- Pseudocode:
	- procedure Merge-Sort(A)
		- if n = 1 then
			- return A
		- m <- floor(n/2)
		- L <- A\[1...m]
		- R <- A\[m+1 ... n]
		- return Merge(Merge-Sort(L), Merge-Sort(R))
	- Soundness: Proof by induction on n
### Merge
- Include brief description of the algorithm, may use pictures also
- General intuition:
	- We have two sorted arrays, we want to have 3 pointers to keep track of the smallest non-used numbers in each of the arrays as well as pointer to the Sort(LR) array to append to.
	- Since arrays are sorted, we compare most-left elements indicated by the pointed from the two arrays and whichever is smaller one gets appended to the Sort(LR) array and the corresponding pointer is appended.
	- Once either of the arrays is exhausted (meaning there are no more elements left) we copy over the left over numbers into main array
	- Operates at O(n+m)
- Input: sorted arrays L\[1...n] and R\[1...m] with n, m >= 1
- Output: Sort(LR)
- Pseudocode:
	- Assuming sentinels L\[n+1] = R\[m+1] = inf
	- procedure Merge(L,R)
	- S <- array of length n+m // initialize array to store two arrays in sorted order
	- i <- 1; j <- 1
	- for k = 1 to n +m do
		- if L\[i] <= R\[j] then S\[k] <- L\[i]; i <- i+1
			- else S\[k] <- R\[j]; j <- j + 1
	- return S
- Soundness either high level vs. formal induction on n+m
- Running time: O(n+m)
### Recursion tree
- Helpful to see recursive calls and analyze the depth of recursion
- For example above, the depth is log(n)
- c \* n work for each depth except the last level where there is a different constant times n (depends on the base case)
- So the total runtime complexity is c times n times log n + another constant times n work for the lowest level --> O(nlogn)

## Sorting Lower Bound
?
- Every comparison-based sorting algorithm takes omega(n log n) comparisons on arrays of length n
- Proof:
	- Every such algorithm for a given n can be modeled as a binary decision tree T
	- Maximum number of comparisons that A makes on arrays of length n equals depth d of T
	- Number l of leaves is at least n factorial
	- Number of leaves is at most 2^d 
	- d >= log(l) >= log(n!)
	- (n/2)^(n/2) <= n! <= n^n, so log(n!) = theta (nlogn)

## Counting Inversions
?
- Inversion in an array is a pair of elements in the array where one's smaller than the other, but it's position is higher
- The bounds on Inv(A) is between 0 when array is sorted and n choose 2 when reverse sorted
### Problem Specification
- Input: array of n integers
- Output: Inv(A) = number of inversions in A
### D&C approach
- Intuition: Split the array into two by the midpoint
	- Count number of inversions in each and combine them as a return result
		- However, this disregards the crossing inversions between both array halves, we need to calculate it linearly
#### Counting Cross Inversions
- Input: sorted array halves (L, R)
- Output: Inv(LR)
- Intuition: Set up the 2 pointers to beginning of sorted arrays 
	- Compare elements at the sorted array pointers, if pointer element of the right array is smaller than a pointer value of the left, increment number of inversions by 1 (from pointer) + number of elements to the right of pointer (can do n - i + 1).
	- If it wasn't smaller or was equal, we don't do anything
	- Lastly increment the smallest element's array's corresponding pointer
- To put it in Pseudocode:
	- procedure Cross-Count(L, R)
		- i <- 1; j <- 1; c <- 0
		- for k = 1 to n+m do
			- if L\[i] <= R\[j] then i <- i + 1
						else j <- j + 1; c <- c + n - i + 1
		- return c
### Count
- Main algorithm for calculating counting inversions
- Pseudocode:
	- procedure Count(A)
		- if n = 1 then 
			- return 0
		- m <- floor (n\2)
		- L <- A\[1...m]
		- R <- A\[m+1...n]
		- return Count(L) + Count(R) + Cross-Count(Merge-Sort(L), Merge-Sort(R))