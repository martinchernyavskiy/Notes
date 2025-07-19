### ISA
- Needed to be known for creation of assembler/compiler and writing programs assembly language
- Specifies all information needed to program in binary 


### LC-3 Architecture
- Processing Unit contains ALU, REG FILE, Multiplexers, and a NZP Detect Logic
- Control Unit contains registers, including PC and IR, multiplexers, an adder that increments PC, FSM, and other logic structures
- Memory connecting to both PU and CU


### LC-3 ISA
- 16 bits wide instructions that are divided into several fields
- 15-12 is 4-bit opcode


### LC-3 Processing Unit
- 8 registers in REG FILE (so 3-bit register address)
- Each register holds 16-bit word and ALU processes 16-bit values
- Some instructions have 2-s complement constant which is called the immediate operand (later sign-extended to 16 bits using SEXT)