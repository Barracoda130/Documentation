## When to use
**Use an 'exception' to handle errors**
Exception class stores information about the type of error and maybe a descriptive string of what went wrong.
EXCEPTIONS CANNOT BE IGNORED!

## Standard Exception Types
- `ArithmeticException`
- `ArrayIndexOutOfBoundsException`
- `NullPointerException`
- `InputMismatchException`
- `FileNotFoundException`
- `IOException`

## Throwing Exceptions
```java
throw new IllegalArgumentException("Invalid amount");
```
If you want to give more information create your own exception class inheriting from the `java.lang.Exception` superclass.

You don't need to throw an exception at every error. If you feel you can handle the error there and then, then do so, but if if not then throwing the exception will let the rest of the code body handle it.

**Should be used when you don't know what to do with the exception**

## Handling Exceptions
Use `try catch` to handle exceptions. Each catch block can be used to handle a different exception type.  You should not throw and catch an exception immediately, then you are doing something wrong.
```java
try {
	// Code that can generate different types of exceptions
}
catch (FileNotFondException error) {
	// Only runs if FileNotFoundException is thrown
}
catch (Exception error) {
	// Runs for any other type of exception
}
finally {
	// Always runs no matter whether exception happened or not
}
```

## Checked and Unchecked Exceptions
**If you write a class that could throw an CHECKED exception, then you need to specify what the class could throw**
```java
public void readFile(String filename) throws IOException {
	// CODE
}
```
Checked exceptions arise from _external factors_ ie. something the programmer has no control over. For example a file not existing, user input not being correct

Either the error must be caught inside the class or it must be 