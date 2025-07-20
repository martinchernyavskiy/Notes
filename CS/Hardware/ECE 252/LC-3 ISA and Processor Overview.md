### ISA
- Needed to be known for creation of assembler/compiler and writing programs in assembly language
- Specifies all information needed to program in binary 


### LC-3 Architecture
- Processing Unit contains ALU, REG FILE, Multiplexers, and a NZP Detect Logic
- Control Unit contains registers, including PC and IR, multiplexers, an adder that increments PC, FSM, and other logic structures
- Memory connecting to both PU and CU
![[Pasted image 20250720143201.png]]

### LC-3 ISA
- 16 bits wide instructions that are divided into several fields
- 15-12 is 4-bit opcode


### LC-3 Processing Unit
- 8 registers in REG FILE (so 3-bit register address)
- Each register holds 16-bit word and ALU processes 16-bit values
- Some instructions have 2-s complement constant (of 5 bits) which is called the immediate operand (later sign-extended to 16 bits using SEXT)

### LC-3 Control Unit

#### Fetch
- CU reads from memory by using PC as the address to read
- DOUT is stored into IR
- PC is incremented 

#### Control Signals
- FSM and instruction decode logic that generate signals to control other parts of processor based on the instruction in IR
- If conditional instruction, output is also affected by condition codes (CCs), which are stored in a special register
	- CCs indicate information about most recent result in PU
	- The signal connected to REG FILE DD also navigates to a separate NZP Detect Logic circuit which determines whether the value is negative, zero, or positive
- Stored in a condition code register where each of control signals are 1 bit and only one of them equals to 1 at any time
- CU updates CCs as part of executing some instruction types (Operate or Load)

#### Memory Address Calc Logic 
- Used for Data Movement instructions
- New PC value for Control instructions
- *addressing mode*: refers to how an instruction specifies the location of its operands
	- memory addressing modes include:
		- Adding offset to a value from the register file
		- Adding 1 or 2 offsets to the PC
		- Determined by Instruction Decode Logic 