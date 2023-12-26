## What are they
Basically like a pointer in C, but they are nicer to use and the syntax is not so annoying. Removes the need to keep using `*` characters. Can also NEVER BE NULL!

## Example
```C++
void swap(int& x, int& y)
{
	int temp = x;
	x = y;
	y = temp;
}

int main ()
{
	int a = 2, b = 7;
	swap(a, b);
	// a = 7, b = 2
}
```
The `&` means a pointer to the datatype. 
The `const` means that I'm doing this for efficiency purposes, I won't change the data of what I'm passing in.

## Uses
- Pointers are much smaller than large objects
- Can be used to 'return' from the function as without `const`  whatever we do to the object passed, will effect the object outside of the function
