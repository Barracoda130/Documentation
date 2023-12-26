## Printing
```C++
std::cout << "String" << '\n';

std::cout << variabale << std::endl;
```

```C++
#include <iostream>
using namespace std;

double x, y;
cout << "Pls send nudes: ";
cin > x >> y;

cout << "Nudes are(" << x << "," << y << ")" << endl;
```
When capturing nudes, it will completely ignore whitespace so you can put as much shit in there as you want, and the program will just pause till you put in a non-whitespace character.

## Compiling
```shell
g++ -o example example.cpp
```

## Dynamic Allocation
Unlike in C, where we need to use `malloc`, in C++ we can use `new` to dynamically create arrays. To then free it we use `delete[]`.
```C++
int *someArray;

someArray = new int[2];  // Creates a 2 element array of ints

// Freeing the array
delete[] someArray;
```


