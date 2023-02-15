## Invoke GDB
```shell
gdb myfile.c
```

## Setup
`set args {arguments}` - set command line arguments for the program

## Commands
`break 52` - break at line 52
`display variableName` - Tracks the contents of a variable
`run` - runs the program from beginning
`next` - steps to next line
`quit` - quit debugger
`break functionName` - breaks at function call

**Displaying Arrays**
`display array@3` - display an array with 3 elements (change 3 to the number of elements)
`display *array@*4` - display an array of strings with 4 elements

## Tips
In GDB if you type a command and then keep pressing enter, it will keep running the initial command