### Insertion Sort
?
- Best case is the array already sorted, worst if 
- Each line has a constant cost, each executed a particular number of times
```Python
def insertion_sort(A):
	for j in range (2, len(A)): # executed n times
		key = A[j] # executed n-1 times
		
		i = j-1 # executed n-1 times
		while i > 0 and A[i] > key:
			A[i+1] = A[i]
			i = i - 1
		A[i+1] = key # executed n-1 times
		
	return A
```