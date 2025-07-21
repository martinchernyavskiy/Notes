### Structured Programming
- Uses 3 fundamental constructs:
	- Sequence
		- *Ordered rectangular subtask blocks with one entry and exit arrows*
	- Selection (condition)
		- *Diamond-shaped decision block in flowchart*
		- One of the two exit paths will be chosen per condition
		- *If/Else*
	- Iteration
		- Uses decision block with one paths leading back to the decision block input repeatedly until the other condition holds
		- *While/For*

### Systematic Decomposition
- Break down complex problems into a set of easier to handle tasks
- Further break down tasks into smaller subtasks that are one step

### Changing the Flow
- Use branch instructions to change PC value
	- *Unconditional branch* - always updates PC
	- *Conditional branch* - updates PC per condition met
- If the branch is taken, meaning that the address is successfully written to the PC, that address is called the *branch target*

### BR Instruction
- Branch target is calculated from incremented PC value and the PCoffset9
- The destination is the PC itself
- There is an NZP field in the instruction which is compared to the current NZP condition code values
	- If any match, the PC is updated with the calculated branch target
	- If none match, PC isn't modified

### BR in LC-3 Assembly Code
- Condition Codes to be checked are appended to the BR opcode mnemonic
- BRn - branch if negative
- BRz - branch if zero
- BRp - branch if positive
- BRnzp - branch if any conditions are true (if use just BR without flags, also interpreted as unconditional)
- *Specified using a label*

### absdiff.asm
```
; Program computes C <- abs(A-B)
; A is R0, B is R1, C is R2
	.ORIG x0200
START
	NOT R1, R1     ; negate B
	ADD R1, R1, #1
	ADD R2, R0, R1 ; A + (-B)
	BRzp SKIPNEG   ; if C >= 0, done
	NOT R2, R2     ; C is negative
	ADD R2, R2, #1 ; so negate it
SKIPNEG
	BR START
		
```