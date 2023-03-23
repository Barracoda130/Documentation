## What are they
Basically like a pointer in C, but they are nicer to use and the syntax is not so annoying.

## Example
```C++
int function(int& number) {}

int function(const int& number) {}
```
The `&` means a pointer to the datatype. 
The `const` means that I'm doing this for efficiency purposes, I won't change the data of what I'm passing in.

## Uses
- Pointers are much smaller than large objects
- Can be used to 'return' from the function as without `const`  whatever we do to the object passed, will effect the object outside of the function
