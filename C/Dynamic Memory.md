## Main functions
### Malloc
Something like:
```C
int *number = malloc( sizeof(int) );
int *number = (int*) malloc( sizeof(int) );
```
I think both of these work, the `(int*)` 

### Calloc
## Returning local variable
When returning a locally defined variable in C, it will have a fit because the variable is 'out of scope', therefore we need to [[#Malloc]]/[[#calloc]] the variable. For example:
```C
int *func() {
	int *num = malloc( sizeof(int) );
	return num;
}
```
This will work.

