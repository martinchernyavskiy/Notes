## Linux Commands
?
- Review with cs 544 sheet (gcc and gdp most important)
	- gcc `file-name` -Wall -m32 -std=gnu99 -o `new-file` -g
	- -g produces debugging information
	- gdb `executable file` allows to debug in real-time
	- b is for setting breakpoints
	- run is for running the program until the break point
	- list is for listing out more lines of code 
		- step: does a single line step
		- next: step over functions
		- continue: runs the program to the end
- *shell-prompt* is the text preceding input cursor ($)
- *network*: cs.wisc.edu

## C Logical Control Flow
?
- Execution starts in main(), top to bottom, sequentially
- C program is a collection of independent functions. We refer to them as functions and not methods since C is not an OOP language
- boolean is not a standard data type in C, instead false is a number 0 and true is any number that is non-zero, including character ASCII values and etc.
	- 0, NULL, '\0' result in false
- *Dangling else* is an else selection statement for which there are more ifs preceding it
- Compiler doesn't see indentations, instead it connects the else statement with the closest if 
	- To address this, we use curly braces to indicate a code block
- *Basic format specifiers*:
	- %i for integer
	- %d for decimal
	- %c for single character
	- %s for sequence of characters (string)
	- %x for hexadecimal number
	- %p for address of memory
	- \n newline character, important for buffer flushing
		- Input is stored in the buffer instead of processing input character by character for efficiency
		- It might be the cause that nothing is get printed out to the output when operating system is accepting the input. This input needs to be "flushed" from the buffer which is accomplished by this newline character
	- If not using the \n to forcefully flush the buffer, it might be sent to output if the buffer gets full or at the very end of the program
- Loops:
```C
// do while loop
int k = 0;
do {
		printf("%i\n", k); // formatted print
		k++;	
} while (k < 11);

// while loop, finite
int i = 0;
while (i < 11) {
		printf("%i\n", i);
		i++;
}

// for loop
for (int j = 0; j < 11; j++) {
	printf("%i\n", j)
}
```

## C Program Structure
?
- C compiler is a one-pass compiler
- *Variables and functions must be declared before they are used*, thus main() is usually at the bottom
- *function*: block of code to accomplish a particular task
- function starts with *return type* and optionally defines a *parameter* in its definition which is an input that the function expects and may do work on.
	- *argument*: data that caller function passes to callee function
	- *parameter*: variable where callee stores caller's data
- *call stack trace*: (stack / heap memory)
	-  *stack memory* is automatically managed by the compiler
		- For example, when program starts, some portion of stack memory is allocated for main() function so that it can store local variables, parameters, or information
		- int x =1; is allocated space on stack memory within *stack frame* of the main function
		- *control is transferred* to bang function
		- consists of stack pointer and base pointer 
	  - *heap memory* used for dynamic memory allocation
		- used to allocate memory at runtime by the user
		- must be explicitly allocated and deallocated via code
- *pass-by-value*: copy of argument value is created
	- when passing an argument to a callee function, it copies the value to a parameter variable, thus it doesn't have access to the original copy of the argument
	- Java contrary to this does *pass-by-reference*
	- Instead we can pass the address of x to change its value directly
- *return-by-value*: copy of the return value
- No built-in data type of string, instead have array of characters which can treat as a string after some processing
- stdio.h header provides printf, fgets
- stdlib.h provides dynamic memory allocation, malloc

## Runtime Description
?
- OS loader reads executable file from disk into RAM, sets up virtual memory space, allocating regions for the code, global variables, stack memory and heap memory.
- Call a special startup routine from C runtime library (crt0 or _start)
- Main is pushed onto the stack, first stack frame is created and pushed on empty stack, containing arguments to main and space for local variables declared inside main
	- If main calls another function, a new frame is pushed on top of main's frame, when retur
## Variables
?
*Primitive unit of storage whose contents can change*
- *Identifier*: the name you give to the variable
- *Value*: data that the variable holds
- *Type*: precedes the variable name
- *Address*: the memory address of the variable
- *Size*: the amount of byte space it takes?
- *Source Operand*: using variable as a value to obtain from
- *Destination Operand*: using variable to store value
- *Byte Addressability*: every memory location is byte addressable
- *Endianess*:
	- *Little endian*:
	- *Big endian*:



