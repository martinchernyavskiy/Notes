### Program Design and Coding
- #### Top-down Design
- Start design at top level and work way down to the subroutine hierarchy
- Develop flowcharts for each subroutine
- #### Bottom-up Coding
- Code up subroutines first to test and ensure they work properly before moving up a level

### strupr design
Start

get char

is null? (T/F)

If not null, convert to uppercase using toupper

save char

increment string pointer

iterate to is null until reach the end of the string

End (string is null)

### strupr
- R1 contains the address of ASCIIZ string
- *Uses pass-by-reference*
- Does not return a result
```asm

```

### toupper
- sub-subroutine, used to assist strupr subroutine
- processes a single lowercase character, making it uppercase and skipping it if it wasn't lowercase to begin with
```

```

### islower
- a sub-sub-subroutine that asissts toupper with determining whether a character is lovercase or not

1111 1111 1111 1011

