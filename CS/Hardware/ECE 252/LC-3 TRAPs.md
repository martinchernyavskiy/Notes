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
- TRAP x20 - GETC service routine
- TRAP x21
- TRAP x22
- TRAP x23
- TRAP x24
- TRAP x25