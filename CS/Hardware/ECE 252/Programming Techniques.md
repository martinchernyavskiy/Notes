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
	ADD R4, R4, #1
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
	ADD R4, R4, #1
	ADD R4, R4, R0 ; A + (-B)
	BRp CgetsA ; taken if A > B
A_LT_B
	BRn CgetsB ; taken if A < B
Cgets0 ; executed if A = B
	AND R2, R4, #0 ; C = 0
	BR REST_OF_CODE
CgetsB
	ADD R2, R1, #0 ; C = B
	BR REST_OF_CODE
CgetsA
	ADD R2, R0, #0 ; C = A

; executed after if, else if, else
REST_OF_CODE
; remaining program code
```


### WHILE Example
```
; while (A < B) A = A + 1
; R0 is A, R1 is B, R2 is C

NEG_B ; loop-invariant code
	NOT R4, R1 ; compute  (-B)
	ADD R4, R4, #1
A_LT_B
	ADD R5, R4, R0 ; A + (-B)
	BRzp REST_OF_CODE ; exit loop if A is greater or equal to B
INC_A ; execute if A < B
	ADD R0, R0, #1 ; increment A
	BR A_LT_B

; executed after if, else if, else
REST_OF_CODE
; remaining program code
```

### DO...WHILE Example
- *Similar to While, but task is performed at least one*
```
; do (A = A + 1)
; while (A < B)

NEG_B ; loop-invariant code
	NOT R4, R1 ; compute  (-B)
	ADD R4, R4, #1

INC_A
	ADD R0, R0, #1

A_LT_B
	ADD R5, R4, R0
	BRn INC_A

REST_OF_CODE
```

### FOR Example
```
; S = 0
; for (i = A; i > 0; i--)
;     S = S + B
; R0 is A, R1 is B, R2 is S

InitializeLoop
	AND R2, R2, #0 ; clear 
	ADD R3, R0, #0
LOOP
	BRnz REST_OF_CODE

; executed after if, else if, else
REST_OF_CODE
; remaining program code
```