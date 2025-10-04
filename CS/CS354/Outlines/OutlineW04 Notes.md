
## stdio.h (standard i/o)
?
- Standard input
	- getchar() reads 1 character from keyboard input
	- gets() reads 1 string ending with a newline character, might result in buffer overflow
		- not recommended, fgets() is the alternative
	- int scanf(const char * format_string, &v1, &v2, ...)
		- Reads formatted input from console keyboard and stored them into specified variables
		- returns # of inputs stored or EOF
		- *Format string contains format specifiers and chars in input to skip*
			- uses format specifiers and whitespace
- Standard output
	- putchar() writes one char
	- puts() writes 1 string up to a newline
	- printf(const char * format_string, v1, v2, ...)
		- writes formatted output to console, returns number of characters written
	- perror(const char * str)
<!--SR:!2025-10-04,3,250-->

## String I/O
?
- int sscanf(const char * str, const char * format_string, &v1, &v2, ...)
	- reads formatted input from the specified str
	- returns number of characters read or a negative if error
- sprintf(char * str, const char * format_string, v1, v2, ...)
	- writes formatted output to specified str
	- returns number of characters written, or negative if error
<!--SR:!2025-10-04,3,250-->

## File I/O
?
- Input:
- fgetc() reads 1 chara at a time
- fgets() reads 1 string up to a newline
- fscaf(FILE * stream, const char * format_string, &v1, &v2, ...)
	- reads formatted input from specified stream
	- returns number of inputs stored
- Output:
- fputc() writes 1 char at a time
- fputs() writes 1 string up to a newline at a time
- int fprintf(FILE * stream, const char * format_string, v1, v2, ...)
	- writes formatted output to specified stream
	- returns number of characters written
<!--SR:!2025-10-04,3,250-->

## Opening and Closing files
?
- Must do before and after reading/writing a file
- fopen(const char * filename, const char * mode)
	- Opens specified filename in the specified mode ("r", "w"dddd)
	- Returns that file's pointer or NULL
- fclose(FILE * stream)
	- flushes output buffer and then closes specified stream
	- returns 0 or EOF
<!--SR:!2025-10-04,3,250-->

## Copying Text Files
?
```
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char *argv[]) {
	if (argc != 3) {
		fprintf(stderr, "Usage: copy inputfile outputfile\n");
		exit(1);
	}
	FILE *ifp = fopen(argv[1], "r");
	if (ifp == NULL) {
		fprintf(stderr, "Can't open input file %s\n", argv[1]);
		exit(1);
	}
	FILE *ofp = fopen(argv[2], "r")
	if (ofp == NULL) {
		fprintf(stderr, "Can't open output file %s\n", argv[2]);
		exit(1);
	}
	if (fclose(ifp) == EOF) {
		fprintf(stderr, "Failed to close input file %s\n", argv[1]);
		exit(1);
	}
	const int buffsize = 257;
	char buffer[bufsize];
	while (fgets(buffer, bufsize, ifp) != NULL) {
		fputs(buffer, ofp);
	}
	fclose(ifp);
	fclose(ofp);
	return 0;
}
```
<!--SR:!2025-10-04,3,250-->

<< --- MIDTERM1 --- >>
## Three Faces of Memory
?
- Use *abstraction* to manage complexity, focus only on relevant details
- The 3 faces of memory include:
	- *Process View (Virtual Memory)*
		- Provides simple view of memory (have more than have physically)
		- *Virtual Address Space* -> illusion by operating system that each process has its own contiguous memory space. Since we have limited computer resources, the actual physical memory oftentimes is shared among the processes, it simplifies to the case where there is an illusion of private resources for each process.
		- The size of the virtual space is 2^32 (since we use a 32 bit computer architecture).
		- Virtual Address consists of Code --> Data --> Heap --> Stack 
		- Memory addresses start from 0x000... to 0xFFF .... The start of the virtual memory address is reserved for the operating system
		- Both Stack and Heap grow/shrink in size
		- At the top of the virtual address we have kernel (memory of the operating system)
		- *Virtual Address* -> simulated address that a process generates
	- *System View (Illusionist)*
		- Make memory sharable and secure
		- Deals with *pages* where pages are memory blocks managed by an operating system (4 KibiBytes for IA-32)
		- *Page table*: OS structure that maps virtual pages to physical pages
	- *Hardware View (Physical Memory)*
		- *PAS*: organized as a multi-level hierarchy that ensures frequently accessed data is close to CPU
		- *Physical address*: actual address to access machine's memory
<!--SR:!2025-10-06,3,250-->

## Virtual Address S