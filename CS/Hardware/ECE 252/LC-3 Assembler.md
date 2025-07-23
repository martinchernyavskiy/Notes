### Assembler
- Software program with:
- Input: Assembly-language source code
- Output: Binary program image

#### Absolute Assembler
- Single assembly source file
- Produces program image (machine code that needs to be loaded into memory
#### Relocatable Assembler
- Produces program image based on *multiple* source code files
- Each source code files is converted into a separate object file
	- Not executable since some have references to parts in other files
- Later joined together by *Linker* into one program image
	- Fixes instructions, joins code and data into single binary program image

### Two-Pass Assembler
- Most assemblers in order to efficiently assemble source code make two passes through a source code file
	- First is to verify syntax and build *symbol table*
		- Table of labels and their addresses in the program
	- Second creates the actual program image
		- Each instruction is encoded and data is allocated 
		- Generates sequence of address:value pairs, listing what must be loaded into memory