## Pointers
?
- Pointer is a scalar variable whose value is a memory address
- Similar to java references (pointers are specific to C and we can do a lot of arithmetic with it)
.
- Allows to have indirect access of memory and functions
- Commonly used in C libraries
- Access to memory-mapped hardware
.
- In representation, we use basic memory diagram and linear memory diagram
	- NULL is represented as a sequence of all zeroes, make sure to include type for basic diagram (\\0 or crossed dash)
	- Unknown address for pointer (when it is uninitialized) is represented by question mark and a horizontal line crossing it. Doesn't mean it is zero since no garbage collector
	- "Pointing" is represented by an arrow
- Pointer is always 4 bytes since it is a memory address, no matter its type
.
- Address operator `&` returns address of a variable
- Pointer: does the pointing (contains memory address of the pointee)
- Pointee: what is being pointed at
- Dereferencing operator (\*): follow address of the pointee
.
- Dereferencing a pointer that is initialized to NULL will try to access memory location 0 which is reserved by OS, results in segmentation fault (no permission to read address)
<!--SR:!2025-10-01,3,250-->

## 1D Arrays on Stack
?
- Compound unit of storage consisting of elements whose values can change
- Accessed by identifier and index
- Allocated as a contiguous fixed-block of memory
.
- Stores collection of data of same data type with fast access
```C
int a[5];
```
- 5 integer elements are allocated memory
- Not initialized, goes on stack
- Memory address of the array is the memory address of the first element. Label a is associated with the first element
- a\[1] = 11;
- Identifier for stack allocated array is not available to be changed
- SAA identifier used as a source operand returns array's memory address
- Using this identifier as a destination operand results in a compiler error
<!--SR:!2025-10-01,3,250-->

## 1D Arrays and Pointers
?
- Address Arithmetic:
	- Computing address of an ith element is given by:
		- Adding array's starting address (label) and a *byte offset* which is i to get to element
		- Offset is automatically scaled based on the data type (size) of element by compiler
		- \*(a+i), dereference has higher precedence than addition, so must enclose in ()
		- i is known as *scaled index*, since when used in address arithmetic it is automatically adjusted by compiler to be multiplied by the byte count of a given data type of the array

## Passing Addresses
?
- Call Stack Tracing
	- *Manually executing code with fns in a manner that mimics the machine*
	- Everytime a function is called, it automatically is allocated a memory stack by compiler to store any local variables, parameters, etc.
		- When function returns, its *stack frame* (memory) is popped from the stack
		- Top function is executing, the functions below waiting for callee to return (LIFO)

## Pass by value
?
- Scalars: scalar parameter that copies the passed in scalar argument
- Pointers: pointer parameter that copies the passed in memory address as argument
- Arrays: pointer parameter that gets a copy of array's address

## 1D arrays on heap
?
- For stack, there are static memory allocations and allocation size is known during the compile time
- For heap, memory is dynamically allocated, allocation is made during the runtime
	- Enables to access more memory than allocated to the program at compile time
	- Uses stdlib preprocessing directory with malloc and free library function
		- malloc returns a *generic* *pointer* (void*) that can be assigned to any pointer type
		- sizeof(operand) returns the number of bytes of an operand
		- int * a = malloc(sizeof(int) * 5)
		- For heap, arrays are creates using malloc and it returns an address type which we save to a scalar pointer variable on the stack which is different from stack allocated array since we're able to change the contents of this pointer unlike the label in SAA