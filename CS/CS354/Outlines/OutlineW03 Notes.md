## 2D arrays
?
- Array of arrays (visualize as a table)
- A pointer to an array of pointers to __ (eg. void** m)
<!--SR:!2025-10-05,4,270-->

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
<!--SR:!2025-10-05,4,270-->

## Address Arithmetic in 2D arrays
?
```C
*(m[i]+j) // access memory of the pointer which is the start of the 1d array and select the element using j byte offset
(*(m+i))[j] // dereference 
*(*(m+i)+j) 
```
<!--SR:!2025-10-05,4,270-->

## 2D arrays on Stack
?
- All elements are located next to each other unlike in heap
```C
int m[2][4] = {{0,1,2,3}, {4,5,6,7}}
```
- Laid out in *ROW MAJOR* order as a single contiguous block of memory
	- All elements are stored in memory row by row
- m is once again a label and not a pointer to the array, can't be changed
<!--SR:!2025-10-04,3,250-->

## Stack and Heap 2D array Compatibility
?
- Type and scale factor
- \*\*m gives m00 which is an int and has no scalar factor
- \*(m+i) gives address of start of row i
	- Scale factor for heap is 4, for stack it's size of row
- m is of type int ** and scale factor is to skip to the address of next row
<!--SR:!2025-10-04,3,250-->

## 2D stack allocated arrays property
?
- m and \*m are same addresses but not the same type
- `*(*m+cols*i+j) is for accessing m[i][j] for stack allocated array only`
- *Basic memory diagram of a SA2DA is a rectangular matrix*
- ![[Pasted image 20250929193815.png]]
- ![[Pasted image 20250929194056.png]]

## Array Caveats
?
- Arrays have no bounds checking or have return types
	- Assigning indices outside of the array bounds results in *buffer overflow*
- SAA requires all but their first dimension to be specified in declaration
	- That is because compiler requires number of columns to find next row
- printIntArray(a, 2, 4);
	- Any array that has same number of columns specified is type compatible with a

## Structures
?
- Basically objects in Java without function declaring
- User-defined type
- A compound unit of storage with data members of different types
- Accessed using its identifier and member selection gets to a particular member
- Contiguous fixed block of memory
```C
struct <typename> {
	<data-member-declaratns>;
};

typedef struct {
	<data-member-declaratns>;
} <typename>;

struct Date {
	// members
	int month;
	int day;
	int year;
};

typedef struct {
	// members
	int month;
	int day;
	int year;
} Date;
```
- struct Date today;
- today.month = 9; *Dot operator is used for member selection*
- struct Date today = {9, 23, 2025}
- When using typedef we don't need to specify `struct Date` for declaration, instead can just use `Date`
- Struct members are uninitialized by default
- Structure's identifier used as a source operand reads the entire struct
	- When used as destination operand, writes the entire struct
- Unlike for arrays where only address is copied over, every member of struct is copied over
- struct Date tomorrow;
- tomorrow = today;

## Nesting in Structures and Arrays of Structures
?
- Structures can contain other structures within them
- Remember, structs are contiguous in memory
```C
typedef struct {
	// members
	int month;
	int day;
	int year;
} Date;

typedef struct {
	char name[12];
	char type[12];
	float weight;
	Date caught;
} Pokemon;
```
-  *Example of stack allocated array of structures*
```C
Pokemon pokedex[2] = {
{"Pikachu", "electric", 43.0, {12, 27, 2005}},
{"Charizard", "fire", 40.0, {12, 26, 2005}}
};
```
- `pokedex[1].weight = 22.2;`
- `pokedex[0].caught.month = 11;`

## Passing Structures
?
- Structs are passed-by-value which copies the whole struct into a parameter, so it can be relatively slow

## Pointers to Structures
?
- Since passing structures to functions copied them as a whole, this is pretty inefficient in terms of memory and instead we can use pointers to the struct declared on stack to change its data members directly
- Enable heap allocation of structs
```C
Pokemon * pmptr = malloc(sizeof(Pokemon))
```
