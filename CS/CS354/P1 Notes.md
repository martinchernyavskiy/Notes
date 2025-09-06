## Build Process Phases
?
*Build Process (Compiling) is a way to translate source code into machine code (file called executable/EOF).*

### Pre-Processing
?
*Prepares a C source file for compiling*
- gcc -E decode.c -Wall -m32 -std=gnu99 -o decode.i
	- -E specifies pre-processing
	- -Wall shows warnings that are generated during the building process
	- -m32 is used for generating code for a 32-bit environment
	- -std=gnu99 is used to tell compiler to use GNU 1999 C standard
	- =0 decode.i saves the output of the command to a file named "decode.i"
- Lines in "decode.c" that start with # which are called *preprocessor directives*
	- L