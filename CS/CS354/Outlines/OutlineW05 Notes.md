## Posix brk & unitstd.h
?
- unitstd.h contains a collection of OS functions used to access functions in the Posix API
- Posix API (portable OS interface): standard for maintaining compatibility among Unix OS
	- Can use Posix calls to manually manage heap

## brk
?
- Program break which is a pointer to the end of program at top of heap
- int brk (void * addr)
	- Sets top of heap to specified address
	- Returns 0 if successful, else -1 and sets `errno`error
	- dangerous to use if passed wrong address

## sbrk
?
- Alternative to brk
- void \*sbrk(intptr_t incr) 
	- intptr_t is signed integer type
	- passing positive value makes the heap grow by incr bytes
	- passing negative value makes the heap shrink by incr bytes
- Returns old brk if successful, else 1 and sets errno

## errno
?
- Set by OS functions to communicate specific error to program code
- \#include \<error.h> 
- printf("Error %s\n", strerror(errno));

## stdlib heap functions vs unitstd.h
?
- In most applications we should use the heap allocation/deallocation functions from stdlib as it reduces the risk of errors. We can use functions from both but it is also not advisable since it may result in undefined program behavior

## stdlib.h
?
- Contains around 25 commonly used C functions of following types:
	- *Conversion*: atoi (ascii to int), atol(ascii to long), strol (string to long) etc.
	- *Execution flow*: exit, abort
	- *Math*: abs, power, etc.
	- *Search*: bsearch
	- *Sorting*: qsort
	- *Random Values*: rand, srand
- *Heap Allocator Functions*:
	- All of these functions return NULL on fail
	- malloc
		- Takes integer input for number of bytes to allocated and returns the address to that heap memory block
	- calloc
		- Allocates memory to heap but also clears memory to zero (meaning the value at each allocated address is 0)
		- Takes in integer arguments
			- First is number of items
			- Second is size of an item (4 bytes for int32)
	- realloc
		- Reallocates (resizes) a previously allocated block of heap memory to new with specified size
			- First argument is the pointer to previous heap memory block
			- Second argument is the new size of bytes
	- free 
		- Frees the heap memory pointed by ptr

## Heap
?
- Segment of process's VAS used for satisfying dynamically allocated memory requests
	- Collection of various-sized memory blocks managed by allocator
- *Dynamically allocated memory*: memory that is requested at runtime
	- *Block*: contiguous chunk of memory that contains:
	- *Payload*: part of block usable by process requesting heap memory
	- *Overhead*: part of block used by allocator to manage heap's structure
	- *Allocator*: a program that allocates and frees heap blocks as well as splits and merges them

## Allocator Approaches
?
- Implicit
	- For example in Java when using "new", heap memory is automatically allocated without having to define a specific size to reserve, it's automatically managed, as well as freed when no longer in use by garbage collector.
- Explicit
	- malloc must be explicitly told how many bytes are needed
	- must free() manually

## Allocator Design
?
- When making design choices, we specify two main goals:
	- 1. Maximize throughput: # of malloc and free requests handled
		- Complexity: O(N) where N is number of heap blocks
		- For free() it is O(1)
	- 2. Maximize memory utilization: percent of heap memory used for payload
		- Maximize payload bytes and minimize overheads
	- Both of these goals have inverse relation

## Design Considerations
?
- "Free block" organization
- Placement policies
- Splitting free blocks to create a better fit
- Merging free blocks to create a larger block

## Heap Linear Memory Layout
?
- Allocated blocks are shaded on the diagram
- Byte addressable
- 1 word is 4 bytes by default
- Block size must be a multiple of 8
- Payload address must be multiple of 8
- *External Fragmentation*: enough heap memory but the blocks are too small to satisfy the request
- *Internal Fragmentation*: when heap memory in block us used for overhead (padding)