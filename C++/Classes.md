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
Also, if a function will not change the class in anyway it should be defined as `const` as shown:
```C++
int getEuros() const;
```

## Constructors & Destructors
#### Constructors
Allocate any extra memory (`malloc`) here (deallocated in deconstructor).
```C++
class Foo 
{
public:
	string name;
	int age;
	Foo(string n, age a)
	{
		name = n;
		cout << "Created" << endl;
	}
}

int main()
{
	// Calling constructor
	Foo f("James");
}
```
C++ has shortcuts to assign variables in constructors. Here is an example of the same constructor.
```C++
Foo(string n, age a) : name(n), age(a) {}
```

#### Destructors
Gets automatically called whenever the class is destroyed, either by garbage collector or buy user.
Make sure you free any memory allocated in the constructor here.
```C++
class Foo 
{
public:
	~Foo()
	{
		cout << "Destroyed" << endl;
	}
}
```

#### Copy constructor
The constructor that is called whenever the class is copied.
```C++
class Foo
{
	Foo(Foo& f)
	{
		cout << "Copied!" << endl;
	}
}
```
## Inheritance
```C++
class Bar {};
class Foo : public Bar {};
```

#### Method overriding
We must declare a method we wish to be able to override as a `virtual` method.
```C++
class Bar
{
	virtual string getName(){}
};

class Foo : public Bar
{
	string getName() {}
}
```

#### Abstract classes
We can also create abstract classes/functions in C++, same as Java. We 'set the function to 0' to do that.
```C++
class Bar
{
	virtual string getName() = 0;
}
```
`getName()` is now an abstract function and must be overwritten in the child class.

#### Constructors
Calling the parent's constructor:
```C++
class Bar{Bar(string n) : name(n){}}

class Foo : public Bar
{
	Foo(string n)
	{
		Bar(n)
	}
}
```

## Templates
Allow us to write more generic classes. Templates are the things in the triangle brackets `<int>` for example.
#### Example
```C++
class matrix <T>  // T is the templated type
{
	int nRows, nCols;
	T **coefficients;
}

// Create instances
matrix<float> floatMatrix;
matrix<double> doubleMatrix;
```