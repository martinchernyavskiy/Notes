*Used for managing complexity which allows to design more and more complex systems and software. Allows for specialized teams to focus on designing one part and not the whole thing.*


## Categories:
?
- ### Software
	Analogous to the UTM's "description of required behavior", representing a away to control the hardware to perform whatever computations are needed.
- ### Hardware
	Physical part of the computer, we focus on the [[processor]] part.

## Abstraction levels:
?
- ### Problem statement
	Human language description of what needs to be done using a computer, the main problem of interest
- ### Algorithm
	Procedures used to perform a particular task, not specific to a particular processor or programming language
- ### Program
	Realization of problem statement, implemented in a particular programming language, implementing algorithm(s)
- ### Instruction Set Architecture (ISA)
	Lies at the boundary of abstraction and specifies the hardware capabilities and how it can be controlled by software.
	Each different ISA defines a particular "machine language". If software is written to speak that language, then it can control any processor designed to listen to it
- ### Microarchitecture
	High-level organization of a processor, determining number of logic circuits, special hard-ware based circuits
- ### Logic Circuits
	Determines the type of circuits to use to accomplish a computation. Designers create structures out of small building blocks, called logic gates, which operates on 1s and 0s, each of which contain multiple transistors. T
- ### Devices