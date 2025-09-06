## Linux Commands
?
- Review with cs 544 sheet (gcc and gdp most important)
- shell-prompt is the text preceding input cursor ($)
- network: cs.wisc.edu

## C Logical Control Flow
?
- Execution starts in main(), top to bottom, sequentially
- boolean is not a standard data type in C, instead false is a number 0 and true is any number that is non-zero, including character ASCII values and etc.
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
- *Identifier*:
- *Value*:
- *Type*:
- *Address*:
- *Size*: