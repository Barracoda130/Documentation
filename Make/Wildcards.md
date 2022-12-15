### %
Let us define a function:
```shell
%.o: %.c
```
The `%` wildcard here can be used to replace anything. 
For example, I can call this using `make file1.o` and the function will read `file1.o: file1.c`. The `%` in the [[Basics#Targets|target]] is the same in the [[Basics#Prerequisites|prerequisites]]. So in this example, the `%` is `file1`.

### $@
For the function:
```shell
%.o: %.c
	gcc input.c -c -o $@
```
The `$@` represents the [[Basics#Targets|target]] of the function (any wildcards included).

### $^ / $<
For the function:
```shell
%.o: %.c
	gcc $^ -c -o output.o
	gcc $< -c -o output.o
```
The `$^` and `$<` meant the same thing and represent the [[Basics#Prerequisites|prerequisites]] of the function (any wildcards included).

### $*
For the function:
```shell
%.o: %.c
	gcc $*.c -c -o $*.o
```
The `$*` represents the `%` wildcard without anything else around it. 
For example, if I ran this function with `make file.o`, `$*` would be `file` without the `.o` extension.