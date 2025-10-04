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
	- (n/2)^(n/2) <= n! <= n^n so 