### Key Info
- Low-level language with one-to-one correspondence between assembly language instructions and machine instructions
- Reduces tedious work that comes from working with binary by using symbolic names for labels and instruction opcodes. Assembler automatically calculates and sets the offset for instructions that access a particular memory address
- Every assembly language is tied to a specific ISA and have different syntax
### Running a Program
- Assemble the source code
- Load program into the memory (real processor includes a special hardware to write the assembled program binary into memory)
- Execute the program

### Debugging
- Takes majority of software development time
- Testing input / output cases give a general idea of whether the program works, however if there are errors, this is the LEAST useful debugging technique to use
- Instead, most debugging tools are equipped with single step execution to analyze code logic per step of the program to determine where is the flaw
	- *Step into*: executes one instruction and pauses
	- *Step over*: same as step into, but for subroutine call, executes the entire subroutine before pausing
- *Breakpoints* allow for running program to a certain instruction