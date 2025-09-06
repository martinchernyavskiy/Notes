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
	int fahr, celsius;
	int lower, upper, step;
	
	// assignment statements
	lower = 0;
	upper = 300;
	step = 20;
	
	fahr = lower;
	while (fahr <= upper) {
		celsius = 5 * (fahr-32) / 9; // 5/9 = 0
		printf("%d/t%d\n", fahr, celsius);
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