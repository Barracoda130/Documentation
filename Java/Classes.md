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

## Upcasting
You can use a superclass as the type for a method/variable and still pass it the subclass and it will be treated as the subclass.
```java
class circle extends shape {}

picture.add(Shape shape);

Circle c = new Circle();
myPicture.add(c);
```
Make sure the superclass has a function definition for the function you wish to call on the Circle/Rectangle objects so you can call it generically.
```java
public abstract class shape {
	public abstract void draw();
}
```
Making the class and/or method abstract means that it can't be called directly. Making the class abstract stops the creation of shape objects. Making the method abstract stops people running the method draw() on a shape object, it can still be called from subclasses if it has been overwritten.

## Inner Classes
Classes can be defined inside other classes, same with [[Enums]]. This allows us to limit the scope of the class so it is only visible to the enclosing class.

#### Example
Works well for playing cards - Rank and Suit only make sense in a playing card context. So the `rank` and `suit` enums could be defined inside the `playingCard` class.

```java
public class Card {
	public enum Rank {...}
	public enum Suit {...}

	private Rank rank;
	private Suit suit;

	public Card(Rank r, Suit s) {...}
}
```
To refer to the `Rank` enum outside the class we need to use `Card.Rank` or `Card.Rank.ACE`.

#### Anonymous Classes
If we define classes inside other classes, we can put them inside any block (if statement, loop etc.), we don't need to actually create a class definition. We can just say `new Class` and automatically create the object. So we don't need to name it.