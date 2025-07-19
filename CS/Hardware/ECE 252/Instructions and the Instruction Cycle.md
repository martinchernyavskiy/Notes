### Program
- Encoded into instructions which are binary smallest possible unit of work for a processor that represent a single step of a program
- Instructions that can be executed are defined by ISA
- Instructions are divided up into fields, each representing info about the instruction
- *Opcode* field indicates the operation type
- Control Unit knows what needs to be done by analyzing the bits of the instructions



### LC-3 ISA
- Instruction set we use in the class
- Use register transfer notation, bits, fields, and bit positions
- 0001 Opcode resembles ADD function

### Operate Instructions
- Use ALU to perform computation
- Mode field specifies which type of addition is described (0 for source register value and 1 for a constant)

### Data Movement Instructions
- *Load*: copy from memory to register file
	- $R1 \leftarrow mem[R5+2]$
	- LDR (0110 opcode) is a type of memory load instruction
	- Control Unit calculates memory address based on the values in base reg and offset fields
- *Store*: copy from register file to memory


### Control Instructions
- Change sequence of instruction execution by changing value in PC
- Loops, Conditions, Subroutines (functions/methods)
	- $PC \leftarrow R6$
	- JMP (1100) is an unconditional jump
	- Copies value in a register (base reg field) to the PC 

### Instruction Cycle
- Special sequence of steps CU takes to process instructions
- Fetch -> Decode -> Evaluate Address -> Fetch Operands -> Execute -> Store Result -> Repeat
- *Not all instructions require all of the steps* 
- Control Unit performs different tasks in each phase, so it's a finite state machine

### Phases required for all instruction types:
#### Fetch
- Read instruction from memory (PC has the address)
- Put value into IR
- Increment PC
#### Decode
- Examine opcode to determine instruction type
- Identify operands based on bit values in instruction's fields

### Required for Operate instructions
- #### Fetch Operands
	- Read from register file using source reg. address(es)
	- If instruction uses constant, extract this value from itself
- #### Execute 
	- After fetching operands, perform the ALU operation
- #### Store Result
	- Write ALU DOUT to register file using destination reg. address 

### Required for Data Move instructions
- ### Load
	- #### Evaluate Address
		- Calculate Memory Address for reading from memory
		- May involve register read and/or constant extraction
	- #### Fetch Operands
		- Read from memory by calculated address
	- #### Store Result (only for writing value to register file)
		- Write the value returned from memory reading into the destination register in the register file
- ### Store
	- #### Evaluate Address
		- Calculate Memory Address for reading from memory
		- May involve register read and/or constant extraction#### 
	- #### Fetch Operands
		- Since we copy value from register to mempry, we read from register value 
	- #### Execute
		-  Value retrieved from register is stored in the memory address calculated first

### Required for Control instructions
- #### Evaluate Address
	- Calculate the memory address to be written to PC
- 