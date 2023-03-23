## What are they
Basically a group of constants like days of the week, months of the year etc.
Enums are classes so we can call methods on them. They have some builtin methods that come with them as they are enums, and we can also define methods inside Enums.

## Definition
```java
enum Day {
	MONDAY,
	TUESDAY,
	WEDNESDAY,
	THURSDAY,
	FRIDAY,
	SATURDAY,
	SUNDAY
}
```
Convention that all values are uppercase because they are constants. These  values are not strings!
Every enum is indexed. Each day in this case is given an index value (like an array) from 0 to the length of the enum.
**If you want to have methods following the enum values, you need to put a semi colon after last value**

## Creating Instance
```java
Day today = Day.THURSDAY;

// Converted from a string
String dayString = "THURSDAY";
Day day = Day.valueOf(dayString);
```

## Methods
Builtin methods for all enums:
`.name()` - Returns string representation of the enum value
`.ordinal()` - Gets the index of the enum value
`.valueOf()` - 
`.equals()` - Compares object to the object inside the brackets. Returns a boolean value
`.compareTo()` - Compares object to the object inside the brackets. Returns an int value that will give info on where compared to the first object the second object is.
`.toString()` - Same behaviour as `name` by default, but can be overriden
`.values()` - Returns an array containing all possible enum values

## Decision Making
```java
switch (day) {
	case MONDAY:
		...
		break;
	case TUESDAY:
		...
		break;
	...
}
```

## Adding Fields
Playing card example
```java
enum Rank {
	ACE('A'), TWO('2'), THREE('3'),...,KING('K');

	private char symbol;

	private Rank(char c) { symbol = c; }

	public char getSymbol() { return symbol; }
}
```