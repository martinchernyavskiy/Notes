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