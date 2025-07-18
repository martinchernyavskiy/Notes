### Program
- Encoded into instructions which are binary smallest possible unit of work for a processor that represent a single step of a program
- Instructions that can be executed are defined by ISA
- Instructions are divided up into fields, each representing info about the instruction
- *Opcode* field indicated the operation type



### LC-3 ISA
- Instruction set we use in the class
- Use register transfer notation, bits, fields, and bit positions
- 0001 Opcode resembles ADD function

### Operate Instructions
- Use ALU to perform computation
- Mode field specifies which type of addition is described (0 for source register value and 1 for a constant)

### Data Movement Instructions
- *Load*: copy from memory to register file
- *Store*: copy from register file to memory