## 2D arrays
?
- Array of arrays (visualize as a table)
- A pointer to an array of pointers to __ (eg. void** m)

## 2D arrays on Heap
?
```C
	int** m; 
	m = malloc(sizeof(int*) * 2) 
	*m = malloc(sizeof(int) * 4)
	*(m+1) = malloc(sizeof(int) * 4)
	If (m == NULL) { 
	  printf("Not enough memory\n");
	  exit(1);
	}
```
- Must check if the memory was allocated successfully
- When freeing memory of 2D array, do this in reverse order

## Address Arithmetic in 2D arrays
?
```C
*(m[i]+j) // access memory of the pointer which is the start of the 1d array and select the element using j byte offset
(*(m+i))[j] // dereference 
*(*(m+i)+j) 
```