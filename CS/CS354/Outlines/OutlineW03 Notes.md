## 2D arrays
?
- Array of arrays (visualize as a table)
- A pointer to an array of pointers to __ (eg. void** m)

## 2D arrays on Heap
?
```C
	int** m; 
	m = malloc(sizeof(int \*) * 2) 
	*m = malloc(sizeof(int) * 4)
	*(m+1) = malloc(sizeof(int) * 4)
	If (m == NULL) { 
	  printf("Not enough memory");
	}
```