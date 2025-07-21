### Flowchart
- Using flowchart is essential before actually starting to code
- Solve the problem at higher level and expect to make revisions
- Use self-descriptive names, but make sure they are short
- Test flowchart before implementation
- *Don't start coding until defined the problem and know how to solve it*
- *Test early and frequently, not when the whole program is completed*

### Assembly IF Implementation Example
```
; increments A if B=0, always update C with its sum with A
; R0 is A, R1 is B, R2 is C

	AND R1, R1, R1 ; updates condition codes to test B
	BRz INC_A ; unnecessary, can be removed
	BRnp UPDATE_C

INC_A ; can be kept since only used by assembler and programmer
	ADD R0, R0, #1

UPDATE_C 
	ADD R2, R2, R0
```

### IF...ELSE Example
```
; if (A > B) C = A
; Implement by subtracting and 
; R0 is A, R1 is B, R2 is C

A_GT_B
	NOT R4, R1 ; compute  (-B)
	ADD R4, R2, #1
	ADD R4, R4, R0 ; A + (-B)
	BRp CgetsA

CgetsB
	AND R2, R1, R1 ; C = B
	BR INC_C
CgetsA
	AND R2, R0, R0 ; C = A

INC_C
	ADD R2, R2, #1
```

### IF...ELSE IF...ELSE Example
```asm
; if (A > B) C = A
; else if (A < B) C = B
; else C = 0
; R0 is A, R1 is B, R2 is C


A_GT_B
	NOT R4, R1 ; compute  (-B)
	ADD R4, R2, #1
	ADD R4, R4, R0 ; A + (-B)
	BRp CgetsA
A_LT_B
	BRn CgetsB
Cgets0
	AND R4, R4, #0
	BR REST_OF_CODE
CgetsB
	ADD R2, R1, #0
	BR REST_OF_CODE
CgetsA
	ADD R2, R0, #0

REST_OF_CODE
; remaining program code
```


### WHILE Example
```

```