## Definition
Made up of .hpp (header) and .cpp files

#### Example
```C++
// .hpp
#pragma once
#include <string>

class Money
{
	public:
		Money(int, int);
		int getEuros() const;
		int getCents() const;
		std::string toString() const;
		Money plus(const Money&) const;

	private:
		int euros, cents;
};
```

The `const` keyword means that the function being called will not change the object state of the object it is being called on at all, for example getters would be `const` but setters would not.
`#pragma once` replaces include guards.

```C++
// .cpp
Money::Money(int e, int c)
{
	euros = e;
	cents = c;
}

int Money::getEuros() const { return euros; }

int Money::getCents() const { return cents; }
```
For every function that is inside the class, you must prefix it with `ClassName::` as shown above with the `Money::`. The constructor is defined as `ClassName::ClassName`.

## Optimisation
#### Compilers
```C++
Money::Money(int e, int c): euros(e), cents(c)
{
	// Other constructor things
}
```
This will set `euros` to `e` and `cents` to `c`. Unfortunately you cannot run error checking before the assignment however with this, though it is slightly faster to do.

#### Calling methods
You can also define small methods like getters and settors inside the header file. This will tell the constructor it can just replace anywhere the methods is called with the actual code. This will make the code run slightly faster. This is called **Inlining**