ints, doubles, chars etc. are always created on the stack

Objects are always created on the heap. To do this you have to use `new`. 
for example:
```java
Scanner input = new Scanner(System.in);
```
`input` is a **reference**, a bit like a C pointer but is safer and doesn't need to be 'referenced'.