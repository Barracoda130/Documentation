## Exceptions
You can use these in C++, though they are not as prominent as they are in Java.

```C++
#include <stdexcept>

if (e < 0)
{
	throw invalid_argument("Invalid Euros");
}
```

#### Catching exceptions
```C++
try {
	...
}
catch {
	...
}
```
We can also specify what kind of error we want to catch
```C++
try {
	...
}
catch (stdexcept::invalid_argument){
	...
}
```