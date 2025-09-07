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
	- long: long integer (32 bits)
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
- Also recognizes %ld for long, %o for octal, %x for hexadecimal, %c for character, %s for character string and `%%` for itself

## For Statement & Symbolic Constants
?
- Symbolic name is replaced by the corresponding replacement text upon compilation, name has the same format as variable. Convention is to write them in upper case
- `#define name replacement list` 
```C
#include <stdio.h>

#define LOWER 0 // lower limit of the table
#define UPPER 300 // upper limit
#define STEP 20 // step size

/* print Fahrenheit-Celsius table*/
int main() {
	int fahr;
	
	for (fahr = LOWER; fahr <= UPPER; fahr = fahr + STEP) {
		printf("%3d %6.1f\n", fahr, (5.0)/(9.0)*(fahr-32))	
	}
}
```

## Character Input and Output
?
- Text input/output is dealt with as *streams of characters*
- *Text stream* is a sequence of characters divided into lines
	- Each line consists of >= 0 characters followed by \n
- getchar(): reads next input character from text stream and returns its value (ASCII)
- putchar(): prints character each time it is called, ASCII --> char
```C
c = getchar();
putchar(c);
```
### File Copying
```C
#include <stdio.h>

/* copy input to output; */
main() {
	int c;
	
	c = getchar;
	while (c != EOF) {
		putchar(c);
		c = getchar();
	}
	
	// second version:
	while ((c = getchar()) != EOF)
		putchar(c);
}
```
- char is meant for storing character data, but it is not large enough to hold EOF which is a special integer value "end of file" defined in stdio.h library, so we use int.
### Character Counting
```C
#include <stdio.h>

/* copy input to output; */
main() {
	double nc;
	
	
	// second version:
	for (nc = 0; getchar() != EOF; nc++) {
		; // null statement, required since for loops MUST have a body
	}
	printf("%.0f\n", nc)
}
```
- double and float both use %f
### Line Counting
```C
#include <stdio.h>

/* copy input to output; */
main() {
	int c, nl, last_c;
	
	nl = 0
	
	while((c = getchar()) != EOF) {
		if (c == '\n') {
			nl++;
		}
	}
	printf("%d\n", nl)
	
	// Excercise 1-9, copy input to output, replacing string of one or more blanks by a single blank
	while((c = getchar()) != EOF) {
		if (c != ' ' || last_c != ' ')
			putchar(c);
		}
		last_c = c;
	} 
}
```
- *character constant*: integer value representing numerical value of the character written between single quotes, one of the machine's character set
- in expressions 'char' is treated as an integer value of the character, but it also resembles a string constant containing one character in other cases
### Word Counting
```C
#include <stdio.h>

#define IN 1 // inside a word
#define OUT 0 // outside a word

/* count lines, words, and characters in input*/

main() {
	int c, nl, nw, nc, state;
	
	state = OUT;
	nl = nw = nc = 0;
	
	while ((c = getchar() != EOF) {
		nc++;
		if (c == '\n') 
			nl++;
		if (c == ' ' || c == '\n' || c = '\t')
			state = OUT;
		else if (state == OUT) {
			state = IN;
			nw++;
		}
	}
	printf("%d %d %d\n", nl, nw, nc)
}

```
- Assignments are associated from right to left
- Expressions connected by logical operators are read from left to right, potentially skipped if a certain condition holds before
## Arrays
?

## Functions
?

## Arguments
?

## Character Arrays
?

## External Variables and Scope
?
