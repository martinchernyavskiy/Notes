## Build Process Phases
?
*Build Process (Compiling) is a way to translate source code into machine code (file called executable/EOF).*
<!--SR:!2025-10-19,16,296-->

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
<!--SR:!2025-10-17,14,290-->

### Compiling Phase (source to assembly)
?
*Translates preprocessed source code to assembly language for a specific processor*
- gcc -S decode.i or decode.c -Wall -m32 -std=gnu99
	- -S indicates to stop after the compilation proper stage and to not assemble
	- Creates the assembler source file
	- Replaces the suffix of the file to `.s` by default
<!--SR:!2025-10-18,15,290-->

### Assembling Phase (assembly to machine code)
?
*Converts assembly language statements into machine code `object code`*
- gcc -C decode.c -Wall -m32 -std=gnu99
	- compiles/assembles source file, but doesn't link
	- can view using *objdump tool*: objdump -d decode.o
		- `objdump` is a disassembler that converts machine code to assembly
<!--SR:!2025-10-19,16,296-->

### Linking Phase
?
*Combines/Links object files to create EOF, including these in standard C library*
- gcc decode.c -Wall -m32 -std=gnu99 -o decode
<!--SR:!2025-10-18,15,290-->