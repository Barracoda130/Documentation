**There are 3 main approaches**

## Something
Use the `java.nio.file` package

1. Create a `Path` object for the file
```java
Path path = Paths.get("filename.txt");
```
2. Then EITHER read the entire file into string (JDK11 onwards)
```java
String text = Files.readString(path);
```
2. OR read lines into a list of strings
```java
List<String> lines = Files.readAllLines(path);
```

## Buffered Reader

```java
Path path = Paths.get(filename);
BufferedReader input = Files.newBufferedReader(path);

String line = input.readLine();

while (line != null) {
	// CODE
	line = input.readLine();
}
```

## Scanner
**Probably easiest and maybe best to use**
```java
Scanner input = new Scanner(Paths.get(filename));

while (input.hasNextLine()) {
	String line = input.nextLine();
}

input.close();
```