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
- shell-prompt is the text preceding input cursor ($)
- network: cs.wisc.edu

## C Logical Control Flow
?
- Execution starts in main(), top to bottom, sequentially
- C program is a collection of independent functions. We refer to them as functions and not methods since C is not an OOP language
- boolean is not a standard data type in C, instead false is a number 0 and true is any number that is non-zero, including character ASCII values and etc.
	- 0, NULL, '\0' result in false
- *Dangling else* is an else selection statement for which there are more ifs
- Compiler doesn't see indentations, instead it connects the else statement with the closest if 
	- To address this, we use curly braces to indicate a code block
- Loops:
```C
// do while loop
int k = 0;
do {
		printf("%i\n", k);
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
- *Variables and functions must be declared before they are used*
- *function*: block of code to accomplish a particular task
- function starts with *return type* and optionally defines a *parameter* in its definition which is an input that the function expects and may do work on.
- The input that actually is passed into the function is called an *argument*
- *caller/callee functions*: caller calls callee
- *pass-by-value* / *return-by-value*, pass in/out 


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



