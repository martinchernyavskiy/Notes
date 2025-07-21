### Indirect Memory Access
- Looking up an address to use for load or store
```
; indirect load, memory too far from instructions
LD R1, ADDR_R
LDR R4, R1, #0

; same as:
LDI R4, ADDR_R

; indirect store, memopry too far from instructions
LD R2, ADDR_W
STR R4, R2, #0

; same as:
STI R4, ADDR_W
```
- Uses hidden special-purpose register as a pointer to far away memory addresses for loading and storing
- The memory addresses are initially stored as contents of labels
- The memory indirect load/store instructions read from the labels and store the 