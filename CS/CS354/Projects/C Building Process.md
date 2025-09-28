## Build Process Phases
?
*Build Process (Compiling) is a way to translate source code into machine code (file called executable/EOF).*

### Pre-Processing
?
*Prepares a C source file for compiling*
- gcc -E decode.c -Wall -m32 -std=gnu99 -o decode.i
	- -E  indicates to stop after the preprocessing stage
	- -Wall shows warnings that are generated during the building process
	- -m32 is used for generating code for a 32-bit environment (IA-32)
	- -std=gnu99 is used to tell compiler to use GNU 1999 C standard
	- =0 decode.i saves the output of the command to a file named "decode.i"
.
- Lines in "decode.c" that start with # which are called *preprocessor directives*
	- Like `#include <stdio.h>`
	- Specify which header files to include to define macros
	- Preprocessing adds header files and expands macros to merge that code within the source file to produce an updated source file
<!--SR:!2025-10-02,4,270-->

### Compiling Phase (source to assembly)
?
*Translates preprocessed source code to assembly language for a specific processor*
- gcc -S decode.i or decode.c -Wall -m32 -std=gnu99
	- -S indicates to stop after the compilation proper stage and to not assemble
	- Creates the assembler source file
	- Replaces the suffix of the file to `.s` by default
<!--SR:!2025-10-02,4,270-->

### Assembling Phase (assembly to machine code)
?
*Converts assembly language statements into machine code `object code`*
- gcc -c decode.c -Wall -m32 -std=gnu99
	- compiles/assembles source file, but doesn't link 
	- can view using *objdump tool*: objdump -d decode.o
		- `objdump` is a disassembler that converts machine code to assembly

### Linking Phase
?
*Combines/Links object files to create EOF, including these in standard C library*
- gcc decode.c -Wall -m32 -std=gnu99 -o decode
<!--SR:!2025-10-02,4,270-->



sequence.c
```C
#import <stdio.h>

int main(int argc, char *argv[]) {
	
	if (argc != 5) {
		printf("Usage: ./sequence n x0 m c   ==> where next value in sequence is computed as x1 = m * x0 + c\n");
		printf("where: n is a non-zero positive number of values in the sequence,\n");
		printf("\tx0 is an integer and is the first value in the sequence,\n");
		printf("\tm is an integer and is used as a multiplier of the previous term in the sequence,\n")
		printf("\tc is an integer and is added to the (m*previous) term\n")
	return 1;
	}
	
	int n = atoi(argv[1]);
	int x0 = atoi(argv[2]);
	int m = atoi(argv[3]);
	int c = atoi(argv[4]);
	
	int current_val = x0;
	
	for (int i = 0; i < n; i++) {
		
		printf("%d",current_val);
		
		if (i < n-1) {
			printf(",");
		}
		
		current_val = m * current_val + c;
	}
	printf("\n");
	return 0;
}
```