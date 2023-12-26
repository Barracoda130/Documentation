# C# Cheat Sheet
## Variables and Constants
#### Datatypes
To create a variable, we must first specify the datatype of the variable. The most commonly used datatypes in C# are:
- `char` - character (one number, letter, or symbol)
- `int` - integer (a whole number - not decimal)
- `float`, `double`, `decimal` - decimal numbers (all these can be treated as the same, however most commonly used is `double`)
- `string` - a series of characters, like a sentence
- `bool` - a boolean (true or false)
#### Defining variables
The format is `datatype` followed by `variable name` and then followed by and `=` sign and a value, and then `;` at the end, however you don't have to assign a value when creating a variable.
```C#
// Creating a variable and giving it a value
int number = 5;
string name = "John";
char = 'r';    // Note how a character has single '' quotes where a string has double "" quotes.

// Creating a variable and not assigning a value
float number2;
bool isMale;
```
#### Constants
A constant is a variable whose value can **NEVER CHANGE**. To define one, define the constant exactly as you would a variable above, except add the `const` keyword before the datatype.
```C#
// This variable will ALWAYS have the value 5
const int number = 5;
```

## Arrays and Lists
#### Difference
Arrays and lists are very similar, however an array CANNOT change size once created, where a list can. When you create an array, you say this array will contain `n` elements (however many you want to put in it), and then that will never change. For a list, when you create it, it has 0 elements in it to start with, and then you can keep adding or removing as many as you would like.
## Arrays
**Cannot change size after being created**
```C#
// Creating an array with values already in it
int[] array = {1,2,3,4};

// Creating an array of 10 elements, but all the elements are empty to start
string[] words = new string[10];
```
The top one will create an array of integers called `array`, with the integers `1,2,3,4` in it.
The bottom one will create an empty array of strings called `words` where every element is blank to start with.
#### Accessing
To access the element at position `n` in the array use the following code:
```C#
// Create the array
int[] numbers = {12, 3, 5, 14, 21};

// Access the 3rd position of the array
int myVariable = numbers[3];
// myVariable is now set to 14 (because array indexing starts at 0)

// Accessing using a variable as the location
int position = 1;
Console.WriteLine(myVariable[position]);
// 3 is printed to the screen
```
#### Getting length
To get the length of an array we use:
```C#
// Create the array
int[] numbers = {12, 3, 5, 14, 21};

int lengthOfArray = numbers.Length;
// lengthOfArray is now set to 5
```
#### Looping through array
We can use a FOR loop to loop through an array and access every element.
```C#
// Create the array
int[] numbers = {12, 3, 5, 14, 21};

for (int i=0; i<numbers.Length; i++)
{
	// Sets arrayElement to each element in the array
	// One at a time, as we loop through the for loop
	int arrayElement = numbers[i];

	// Prints that element to the screen
	// This line is not necessary - just a way to demonstrate how to use it
	Console.WriteLine(arrayElement);
}
```

## Lists
**Can change size after being created**
```C#
// Create a new list with values already in it
List<int> list = new List<int> {1,2,3,4,5};

// Create a new empty list
List<string> otherList = new List<string>();
```
The top one will create a list of integers called `list`, with the integers `1,2,3,4,5` in it.
The bottom one will create an empty list of strings called `otherList` with no elements in it to start with.
#### Accessing
To access the element at position `n` in the list use the following code (it is exactly the same as for an array):
```C#
// Create the list
List<int> myList = new List<int> {12, 3, 5, 14, 21};

// Access the 3rd position of the list
int myVariable = myList[3];
// myVariable is now set to 14 (because list indexing starts at 0)

// Accessing using a variable as the location
int position = 1;
Console.WriteLine(myList[position]);
// 3 is printed to the screen
```
#### Adding/Removing
Unlike an array, for lists, we can add to the end, and remove from the list.
```C#
// Create the list
List<int> myList = new List<int> {12, 3, 5, 14, 21};

// Add to the end
myList.Add(12);
// myList now looks like {12, 3, 4, 14, 21, 12}
// 12 has been added to the END of the list, and the list is now 1 element LONGER

// Removing from list
myList.Remove(3);
// myList now looks like {12, 4, 14, 21, 12}
// 3 has been removed from the list, and the list is now 1 element SHORTER
```
#### Getting length
To get the length of an list we use:
```C#
// Create the list
List<int> numbers = new List<int> {12, 3, 5, 14, 21};

int lengthOfList = numbers.Count;
// lengthOfList is now set to 5
```
#### Looping through list
We can use a FOR loop to loop through an list and access every element (it is almost exactly the same as for an array).
```C#
// Create the list
List<int> numbers = new List<int> {12, 3, 5, 14, 21};

for (int i=0; i<numbers.Count; i++)
{
	// Sets arrayElement to each element in the list
	// One at a time, as we loop through the for loop
	int listElement = numbers[i];

	// Prints that element to the screen
	// This line is not necessary - just a way to demonstrate how to use it
	Console.WriteLine(listElement);
}
```
## Operators
#### Maths operators
- `+` add two numbers or strings
- `-` subtract two numbers
- `*` multiply two numbers
- `/` divide two numbers - will always give an integer if either number is an integer, will give a decimal if both numbers are decimal numbers (float, double, decimal)
- `%` take the modulus of two numbers - divide the first by the second and give the remainder
#### Conditional symbols
- `a == b` Check if the value of `a` is equal to the value of `b`
- `a < b` Check if `a` is smaller than `b`
- `a > b` Check if `a` is larger than `b`
- `a <= b` Check if `a` is smaller than or equal to `b`
- `a >= b` Check if `a` is larger than or equal to `b`
- `a != b` Check if `a` is NOT equal to `b`

## Input and Output
#### Input
```C#
string userInput = Console.ReadLine();
```
Whenever taking input from the user, it will always be a string.
#### Output
```C#
// Output text
Console.WriteLine("Text");

// Output variable
int variable = 5;
Console.WriteLine(variable);
```

## Conditionals
#### IF statements
An IF statement is used to do one thing or another depending on whether a condition is true or false.
```C#
if (number == 5)
{
	// Run this if the variable number is 5
}
else
{
	// Run this if the variable number is NOT 5
}
```
We can also use `else if` blocks if we want to check for a few different scenarios.
```C#
if (name == "John")
{
	// Run this if name is "John"
}
else if (name == "Steve")
{
	// Run this if name is "Steve"
}
else
{
	// Run this if name is NOT "John" AND NOT "Steve"
}
```
#### Switch statements
These are very similar to IF statements. They are used to do different things based off of the value of one single variable. 
```C#
switch (number)
{
	case 5:
		// Run this if the number is 5
		break;

	case 6:
		// Run this if the number is 6
		break;

	case 10:
		// Run this if the number is 10
		break;
		
	default:
		// Run this if the number is NOT 5, NOT 6, AND NOT 10
		// Will run only if NONE of the case conditions are met
		break;
}
```

## Loops
#### While loops
Runs the code inside the loop until the condition inside the brackets is True.
```C#
while (condition)
{
	// Run this code until the condition is true
}

// Example
string userInput;
while (userInput != "no")
{
	// This will keep printing until the user types "no"
	Console.WriteLine("Would you like to continue running? ");
	userInput = Console.ReadLine();
}
```
#### For loops
Example:
```C#
for (int i = 0; i < 5; i++)
{
	// Run the code inside here
}
```
For loops in C# have 3 parts to their definition:

**Variable definition:**
This if the first thing inside the brackets - in this example it is `int i = 0;`. This does exactly what you would expect from having read the Variables and Constants section of this document - it creates an integer variable called `i` and sets it to `0`.

**Condition:**
The condition is the second thing inside the brackets - in this example `i < 5`. The for loop will run *while this condition is **True***. So in this example, the for loop here will run WHILE `i` is less than `5`.

**Change to the variable:**
The last thing in the brackets is what happens to the variable every time the for loop loops (runs the instructions inside the loop once) - in this example it is `i++`. `i++` is a fancy way in C# to write 'add one to `i`'. This means, that every time this loop runs, `1` is added to `i`. 

The result of all of this is that for this example, the variable `i` will start at `0`, then every time the code inside the loop runs once, `1` is added to `i`. This loop will continue to do this till `i` is NOT less than `5`. Therefore this loop will run 5 times, with `i` being `0`, `1`, `2`, `3`, `4` respectively each time the code inside the loop runs.

(I'm not super happy with this explanation, I'll explain again in the lesson)

## Functions
A function is a chunk of code that is given a name and then run whenever that name is called.
#### Real life example
An example of a function is you making a cup of tea. When you make a cup of tea, you: 
1. get a teacup
2. boil the water
3. put the water in the cup
4. add the teabag
5. add the milk
6. add the sugar
7. etc.
That is a lot of steps and when you are programming, you don't want to be writing these steps out 15 times if you need to make 15 cups of tea. So we can save these instructions inside a _function_ called `makeTea` and then whenever we want to make tea, we can just call the function `makeTea` and it will run all these steps, without us having to write them all out again.

```C#
// Define the function
static void makeTea()
{
	// get teacup
	// boil water
	// ...
}

// Call the function (run the makeTea function)
makeTea();
```
This is a very basic function that will make us a cup of tea in C#.
#### Parameters
Imagine we now want to make tea for 3 different people, but 2 of them want milk and no sugar, where the 3rd wants milk AND sugar. Now we could create 2 different functions, one of them that adds milk and no sugar, and the other that adds both, but there is a much easier way of doing it.

Parameters are a way of giving the function some extra information and making a function able to work in more than just one scenario.
```C#
// Define the function
static void makeTea(bool wantMilk, bool wantSugar)
{
	// get teacup
	// boil water
	// ...
	if (wantMilk == true)
	{
		// Add milk
	}
	if (wantSugar == true)
	{
		// Add sugar
	}
}

// Call the function (run the makeTea function)
// First two people want milk and no sugar, so we tell the function
makeTea(true, false);
makeTea(true, false);

// Last person wants both milk and sugar
makeTea(true, true);
```

#### Returning
Imagine now, that when making the tea we run out of sugar, DISASTER!! We now need a way though of telling the person who asked us to make the tea that we have failed them and run out of sugar so they can then make a decision whether they still want us to make the tea for them.

Returning is a way of a function giving information (like running out of sugar) back to whatever called it. We change the second word (`void` in the function above) to whatever datatype we would like to return. Then at the end of the function, we write `return ____` and replace the `____` with whatever we want to return. That thing we return can then be stored in a variable and used later in the program as shown below.
```C#
// Define the function
// We have replace 'void' with 'string' here as we want to return a string
static string makeTea()
{
	// Create a variable containig our success message
	string successMessage = "Tea successfully made!";
	
	// get teacup
	// boil water
	// ...
	// Check to see if we have run out of milk or sugar
	if (runOutOfIngredient)
	{
		return "HELP! We have run out of either milk or sugar!!";
	}
	else
	{
		// We can also return variables, not just strings/ints
		return successMessage;
	}
}

// Call the function (run the makeTea function)
// The string 'message' becomes whatever the function returns
string message = makeTea()

// We can then output the message
Console.WriteLine(message);
```
**N.B: If your function ever runs a `return` statement during execution of it, the function will IMMEDIATELY END, no matter how much code you have after that statement.**

## Classes
#### What are classes
Classes are like templates, they can then be _instantiated_ (when you create an _object_ from a class). This object, is now a copy of that template, except it is 'alive' and can now be used in our program. You can think of it like this: imagine you create a 3D model of a car gear box on your computer. That 3D model is like a class - it is a template that can then be instantiated. When you then use your 3D printer to print that model, that is like creating an object - instantiating your class. You can't use your model when it is on the computer, but once you have printed it, you can then use it.
#### Why use classes
Classes are really good at grouping information together. Think of any object you can, we will use the example of a fridge. This object has a lot of information that relates specifically to it. In this example, the fridge will have contents (the food inside), a temperature, a make, a model etc. Every fridge will have these things, but they aren't necessarily the same for every fridge - my fridge may have tomatoes in it, where your fridge does not. When we create an object from our class, we can then set information specifically for that object. So my fridge will be one object, with tomatoes as one of the contents, and your fridge will be a different object, without tomatoes as one of the contents.
When you are programming, if you are faced with a problem, try to break it down into things you can create into their own classes.
#### Creating
**Constructor:** A constructor is a function that is called whenever an object is created from the class. It is a function you can use to set variables as shown below, and run any functions you want to when the class is created.
```C#
// Create a class called Person
class Person
{
	// Define any attributes (variables) associated with the class
	private string name;
	private int age;
	private string email;

	// Create a constructor for the class
	// The name of the constructor MUST be the same as the name of the class
	public Person(string _name, int _age, string _email)
	{
		// We now set the attributes of the class to the variables passed 
		// into this function
		name = _name;
		age = _age;
		email = _email;
	}

	// We can also created methods (subroutines) that relate to the class
	// For example, all people can eat food so we can create a method for that
	public void eatFood()
	{
		// Code to eat food
	}

	// We could also create a method that prints out a business card for 
	// that person
	public void businessCard()
	{
		Console.WriteLine($"Name: {name}\n Age: {age}\n Email: {email}")
	}
}
```
**Access:** You will notice above I keep using the words `public` and `private`. These determine where you can access that variable/method from. Any variable/method with the word `private` in front of it, can only be accessed from within the class, and any method with the word `public` in front of it can be accessed from anywhere in the program.
#### Inheritance
