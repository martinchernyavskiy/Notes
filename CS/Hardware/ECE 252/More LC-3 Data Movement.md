### LDR and STR 
- Base+Offset addressing
- *Base register* is 1 out of 8 general purpose registers that acts as a base address
- Offset indicates how far away the effective address is from where the base register is pointing

#### LDR
```
LDR DR, BaseR, offset6 ; format

; examples
LDR R5, R1, #2
```
#### STR
```
STR SR, BaseR, offset6
```


### LEA (load effective address)
- Copies a label's address to a register, can later be used as a base register
```
LEA R1, ARRAY
```


### array_sum.asm
```asm
; This program adds the values in an
; array with three Locations.
; R0; sum, R1: array pointer, R2: temp

	.ORIG x0200
START

	LEA R1, ARRAY ; get ARRAY address
	LDR R0, R1, #0
	LDR R2, R1, #1
	ADD R0, R0, R2
	LDR R2, R1, #2
	ADD R0, R0, R2

	BR START
ARRAY .FILL x00F0
	  .FILL x0010
	  .FILL x2002
	  .END 
```