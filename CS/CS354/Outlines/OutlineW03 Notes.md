## 2D arrays
?
- Array of arrays (visualize as a table)
- A pointer to an array of pointers to __ (eg. void** m)

## 2D arrays on Heap
?
- The arrays that array of pointers point to may not be stored next to each other
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

## 2D arrays on Stack
?
- All elements are located next to each other unlike in heap
```C
int m[2][4] = {{0,1,2,3}, {4,5,6,7}}
```
- Laid out in *ROW MAJOR* order as a single contiguous block of memory
	- All elements are stored in memory row by row
- m is once again a label and not a pointer to the array, can't be changed

## Stack and Heap 2D array Compatibility
?
- Type and scale factor
- \*\*m gives m00 which is an int and has no scalar factor
- \*(m+i) gives address of start of row i
	- Scale factor for heap is 4, for stack it's size of row
- m is of type int ** and scale factor is to skip to the address of next row

## 2D stack allocated arrays property
?
- m and \*m are same addresses but not the same type
- ![[Pasted image 20250929193815.png]]
- ![[Pasted image 20250929194056.png]]

## Array Caveats
?
- Arrays have no bounds checking or have return types
	- Assigning indices outside of the array bounds results in buffer overflow
