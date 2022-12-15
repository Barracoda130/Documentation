## Compiler conational statements

```C
#ifdef DEBUG
	printf("Debug");
#endif
```
OR
```C
#ifndef DEBUG
	printf("Not debug");
#endif
```

## Defining variables at compile time

```shell
gcc -D DEBUG file.c -o file
```
OR
```shell
gcc -D TEST file.c -o file
```
