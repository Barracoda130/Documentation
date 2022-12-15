## Command format

```shell
targets: prequisites
	command
	command
	command
```

### Targets
This is like the name of the function. If the target is `hello` and I type `make hello` then that is what will run. 
The target doesn't have to be the exact name of something, you can use [[Wildcards]] to run the same function under multiple names.

### Prerequisites
These are what the function requires to run. For example, if the function is supposed to convert .c files to .o files, it requires the .c files in the first place. 
You can also put other makefile functions as a prerequisite, and it will run those before. 
Prerequisites are run in the order they are written (left to right).

### Command
You can run any shell command here. You can also use [[Wildcards]] to get the data of the [[#Targets]] and [[#Prequisites]] for this function. 

## Variables
### Assign variables
To assign a variable, type:
```shell
VARIABLE := sometext
VAR2 = some other text
```

If we want the variable to be assigned to something and we need to run a command line function to get that something, we can do it like this:
```shell
VARIABLE := $(shell find *.c)
```
*Make sure you put the word `shell` in*

### Using variables
When using a variable, it will replace its name with exactly what it contains, similar to `#define` in C.
```shell
DIR := src/
run: 
	ls $(DIR)
```
The code here will list everything in the `src` directory. 

## Commenting
Put a `#` at the start of a line to make that line a comment.
You can cannot comment inside functions, only outside of them for example:
```shell
# Runs the program
# Replace clear with: @echo -e '\n \n \n'
# if you want to still see the compiler output
# These comments are all fine
run: $(TARGET)
    clear
    # This comment will crash the program as it will treat it as a command
    ./$(TARGET)
```
It will treat any comments in the command section as commands and therefore will crash the program.