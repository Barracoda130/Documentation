## What
An interface is a purely abstract class, where the class is not instantiable and none of the methods are able to be called, but it can be inherited from.

## Setup
- No constructor
- No fields but can define constants
- Methods are implicitly public and abstract
- Defined using the `interface` keyword

## Definition
Interface names often end in 'able' because they often specify capabilities
```java
public interface Printable {
	void print();
}

public class Document implements Printable {
	public void print() {
		// Code to actually print document goes here
	}
}
```

## Uses
Classes can only inherit from one superclass but it can implement many interfaces
Instead of defining variables of type superclass, we can define them as type of interface