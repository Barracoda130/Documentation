## Association
One class can call the methods of the other class.
This is done through having an instance of one of the classes inside another.
```java
class Employee {
	private Company employer;

	public void main() {
		Company.getStock();
	}
}
```

#### Composition/Aggregation
- One class (the 'composite') has component parts that are represented by another class.
- Can be represented in code by association
- Basically special words for certain Associative relationships
Aggregation is where ownership is 'Weak' - a component part can be part of two separate composite classes.
Composition is where ownership is 'Strong' - a component part can only be part of one composite class.
```java
class Band {
	private Set<Musician> members;

	public void join(Musician musician) {
		members.add(musician);
	}
}
```

## Inheritance
Subclass `extends` superclass
```java
public class Person {
	private String fName;
	private String sName;
	private LocalDate dateOfBirth;
}

public class Student extends Person {
	private String degree;
	private YearMonth start;
	private Set<Module> modules;
}
```

#### Invoking superclass constructor
```java
public class Student extends Person {

	public Student() {
		super(paramsForSuperClass);
	}
}
```
`super();` Calls the superclass constructor
`super.method();` - Call method from superclass

#### Method overriding
Put an `@override` on the line before the method definition to say that you intend to override that method later. Also do this for the overriding method.

**Protected** fields/methods means that any subclasses can access those fields/methods
**Final** Can be used to prevent inheritance/overloading:
```java
public class final Student {
	// Prevents inherritance
}

public class Student {
	public final int getBirthday() {
		// Prevents method overriding
	}
}
```