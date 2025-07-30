### LC-3 Operating System
- Must be assembled and loaded into memory
- Processor starts at 0x0200, but it's part of the OS code, so instead OS jumps to 0x3000 to run the application.
- OS automatically jumps to 0x3000, so the application code must be in that area of memory beforehand


### TRAPS
- Instructions to request an OS service, causing OS to execute *service routine or TRAP handler* and return to the application code when finished
- Basic I/O services provided by LC-3 OS include reading from keyboard and writing to the console display

### TRAP instruction
- Opcode: 1111
- 8-bit operand that indicates which OS service is requested
- Similar to subroutine call (*indirect subroutine call*), but uses the OS service code to look up address of a routine in the vector table, consisting of 256 entries at addresses x0000-x00FF that contain starting addresses of OS service routines

- Incremented PC is saved into the R7
- Trap vector code is *zero-extended* to 16 bits
- Used as the address for memory read that gets the service routine start address from *vector table* that is then written to the PC

### TRAP Codes
- TRAP x20 - GETC (wait for keyboard character)
	- Returns character to R0
- TRAP x21 - OUT (write character to console display)
	- Writes character in R0 to console display
- TRAP x22 - PUTS (write string to console display)
	- Writes string with starting address at R0 to console display
- TRAP x23 - IN (prompt and wait for character)
	- Writes prompt to display ("Input a character>") and waits for keyboard character which is returned in R0
	- Echoes the typed character in R0 to the console display before returning
- TRAP x24 - PUTSP (not used in 252)
- 
- TRAP x25 - HALT (transfer control to OS and restart)

- LC-3 assembler allows to use alias for using TRAP instructions and during assembly it just substitutes the actual instruction in place of alias
- Any other TRAP request is vectored to a "bad trap" handler in OS which prints out an error message to the console