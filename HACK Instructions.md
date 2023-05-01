## File
File extension `.asm`

## Loading and storing to memory
`@100` - Sets the `A` register to 100 (or any number)
`M` register - Gets the memory location a the constant stored inside `A`
```assembly
// Sets the D register to whatever is in memory location 50
@50
D=M;

// Sets the D register to the VALUE 50
@50
D=A;
```

```assembly
// Store whatever is in the D register to memory location 12
@12
M=D;
```

## Branching
```assembly
// If D is equal to 0 then jump to instruction in address 6
@6
D;JEQ
```

## Variables
Memory location 0, 1,...,15 have the variable name R0, R1,...,R15. If I want to define my own variable, then it will automatically set it to the next number available after 15. 
eg.
```assembly
@i  // Memory address 16
@b  // Memory address 17
...
```
Should be written in lowercase/camel case

## Labels
Used to jump to sections of code. Used for loops and other tings.
```assembly
(LOOP)
	@i
	...
	@LOOP
	0;JMP

(CONT)
	...
```

## Terminating program
```assembly
(END)
	@END
	0;JMP
```