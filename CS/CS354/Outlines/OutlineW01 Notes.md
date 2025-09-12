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
- string.h for manipulaing c strings (array of characters with a null terminating character at the end of array)
- *Global variable*: is a variable declared outside of functions and can be freely used from any function. Declared at the top of the file 
- int main(int argc, char \*argv[])
	- *CLA*: command line arguments, allows to pass extra information to program by passing these
	- ./prog1 arg1 arg2 : name of executable is also counter as one of the CLA, so this command line include 3 command line arguments
	- *argc* keeps track of the number of command line arguments, which in this case is 3
	- given an asterisk, it indicates a pointer variable which you read from right to left.
		- argv is array of pointers to characters
- char * input_string = malloc(N); 
	- malloc reserves a heap memory block of N bytes, returning the address of the memory location it has reserved.
	- Must therefore save the address to a pointer variable

## Runtime Description
?
```
### 1. Compile Time: Creating the Blueprint 📜

It all starts with your source code in a `.c` file. You run a compiler (like GCC), which translates your code into an executable file.

This executable file is a highly organized blueprint. It contains several key sections:

- **Text Segment (`.text`)**: The actual machine code instructions for all your functions, including `main`. Its size is fixed.
    
- **Data Segments (`.data`, `.bss`)**: These sections describe the size and initial values (or lack thereof) for all your global and static variables. Their sizes are also fixed.
    

At this point, your program is just a dormant file on your hard drive. No memory has been allocated, and nothing is running. The compiler has simply written the step-by-step instructions for how to build and run the program later.

---

### 2. Runtime: The Program Comes to Life 🚀

When you run the executable, the operating system (OS) takes over.

1. **Loading**: The OS loader reads the executable file. Following the blueprint, it allocates memory for your process. It loads the machine code into the **Text Segment** and sets up the **Data Segment** for your global variables.
    
2. **Stack & Heap Creation**: The OS allocates a block of memory for the **stack** (typically a default size like a few megabytes) and sets up the mechanisms for the **heap** to grow on demand.
    
3. **The First Push**: The OS hands control to a small C runtime startup routine (linked in during compilation). This routine's final job is to call your `main()` function. This call places the very first **stack frame** onto the now-active stack.
    

---

### 3. Execution: The Ebb and Flow of Memory 🌊

Now, your code inside `main` begins to execute instruction by instruction.

- **Calling Functions**: When `main` calls another function, say `calculate()`, a new stack frame for `calculate()` is pushed on top of `main`'s frame. This new frame holds `calculate()`'s local variables and parameters. The **stack pointer** register in the CPU keeps track of the top of this ever-growing and shrinking stack.
    
- **Returning from Functions**: When `calculate()` finishes and returns, its stack frame is popped off. All its local variables are instantly gone. The stack pointer moves back down, and execution continues in `main` right where it left off.
    
- **Using the Heap**: If your code calls `malloc()`, you are requesting memory from the heap. The C library's memory manager finds a suitable spot in the heap. If the heap is out of space, it asks the OS for more, and the heap grows. This memory is yours to keep until you explicitly call `free()`. It is completely independent of the function-call-based stack.
    
- **Errors**: If you have runaway recursion, the stack will keep growing until it exhausts its pre-allocated block, causing a **stack overflow**. If you keep calling `malloc` without `free`, the heap will keep growing, potentially consuming all available system memory and causing an **out-of-memory error**.
    

---

### 4. Termination: Giving it All Back 🏁

Eventually, your `main` function finishes and returns.

1. **Final Pop**: The return from `main` pops its own stack frame off the stack. Control is given back to the C runtime startup routine.
    
2. **Exit**: The startup routine communicates the program's return code to the OS and tells it the program is done.
    
3. **Cleanup**: The OS cleans up everything. It reclaims **all** memory associated with the process—the text, data, stack, and heap segments are all wiped away, and the resources are returned to the system for other programs to use.
```

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



