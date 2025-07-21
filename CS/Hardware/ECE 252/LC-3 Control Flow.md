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
- There is an NZP field in the instruction for which if one of the condition codes 