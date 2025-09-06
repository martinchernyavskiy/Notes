## C Program Contents
?
- C is a *statically typed* (meaning you must declare types of variables), but *weakly typed*  (meaning you can do operations on different data types)
- Consists of functions (containing *statements*) and variables
- main is a special function, this is the function where the program starts executing
- Preprocessor directives are used for compiler to include information about the specified library
- printf is a library function that takes in character string argument
```C
#include <stdio.h>

int main() {
	printf("Hello World!\n)
}
```

## Variables and Arithmetic Expressions
?
- Comments are identical to Java
```C
#include <stdio.h>

/* print Fahrenheit-Calsius table
	for fahr = 0, 20, ..., 300 */
	
void main() {
	float fahr, celsius;
	float lower, upper, step;
	
	// assignment statements
	lower = 0;
	upper = 300;
	step = 20;
	
	fahr = lower;
	while (fahr <= upper) {
		celsius = (5.0/9.0) * (fahr-32.0);
		printf("%3.0f\t%6.1df\n", fahr, celsius);
		fahr = fahr + step;	
	}
}
```
- *Data Types*
	- *Size of these objects is machine dependent*
	- char: character (single byte)
	- short: short integer
	- long: long integer
	- double: double precision floating point
	- int
	- float, at least 6 significant digits
- Indentation emphasizes logical structure of the program, critical for humans, not required for compilers
- Integer operands --> Integer operation.
- Floating-point operand + int operand --> floating-point operation since int will be automatically converted to a floating point number

| %d    | print as decimal integer                                  |
| ----- | --------------------------------------------------------- |
| %6d   | print as decimal integer, at least 6 characters wide      |
| %f    | print as floating point                                   |
| %6f   | print as floating point, at least 6 characters wide       |
| %.2f  | print as floating point, 2 characters after decimal point |
| %6.2f | print as floating point, >6 wide, 2 after decimal poont   |
- Also recognizes %o for octal, %x for hexadecimal, %c for character, %s for character string and `%%` for itself

## For Statement
?
```C
#include <stdio.h>

int main() {
	int fahr;
	
	for (fahr = 0; fahr <= 300; fahr = fahr+20) {
		printf("%3d %6.1f\n", fahr, (5.0)/(9.0)*(fahr-32))	
	}
}
```