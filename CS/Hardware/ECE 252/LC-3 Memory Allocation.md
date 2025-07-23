### Terminology
- Data allocation directives allow for setting up memory space for variables to use in the program.
- Labels are used as symbolic addresses, the assembler chooses the actual addresses
- *Allocate*: reserve space in memory
	- No code or variable will be placed there
- *Initialize*: set value in memory location when program is loaded
	- Happens before program executes


### Memory Allocation Directives
*Label is optional symbolic address of the first word of memory allocated*

- #### \<Label>   .FILL value
	- Allocates one location and initializes it to value
- #### \<Label>   .BLKW count
	- Allocates count words of memory, not initialized
- #### \<Label>   .STRINGZ "string"
	- Allocates and initializes memory to hold ASCIIZ string (null terminates sequence of ASCII characters)