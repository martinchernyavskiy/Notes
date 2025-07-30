### LC-3 Operating System
- Must be assembled and loaded into memory
- Processor starts at 0x0200, but it's part of the OS code, so instead OS jumps to 0x3000 to run the application.
- OS automatically jumps to 0x3000, so the application code must be in that area of memory beforehand


### TRAPS
- Instructions to request an OS service, causing OS to execute *service routine or TRAP handler* and return to the application code when finished
- Basic I/O services provided by LC-3 OS include reading from keyboard and writing to the console display

### TRAP instruction
- Opcode: 1111
- 8-bit operand that indicates which OS routine is requested
- 