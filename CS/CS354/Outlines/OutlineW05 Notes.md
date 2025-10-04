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
	- Returns 0 if successful, else -1 and `errno`error
	- 