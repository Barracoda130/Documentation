# Printing
```java
System.out.println("What i want to print: \n");

System.out.printf("%4.1f miles = %4.1f km\n", distanceMiles, distanceKm);
```
For format strings, `%4.1f` means that it prints a float, that is 4 characters long, no matter how many numbers are actually used and it uses 1 decimal place.

# Input
### Scanner
```java
Scanner input = new Scanner(System.in);

double distanceMiles = input.nextDouble();
```
For this example, the scanner will scan over any characters the user input, ignoring whitespace like tabs and return keys, and look for something it can turn into a double.

Scanner can also be used to scan through files, not just the user input stream.

### Console
```java
Console con = System.console();
String input = con.readLine("Enter a distance: ");

double distanceMiles = Double.parseDouble(input);
```
Console is more like `input()` in python. Will return only text which then needs to be converted.
Normally `Scanner` is better, but console can be used and is particularly useful for passwords.