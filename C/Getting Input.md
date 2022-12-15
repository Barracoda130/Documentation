```C
#include <stdio.h>

int main(void) {
	int bufferLen = 12;
    char buffer[bufferLen];
    int DOB[3];

    printf("What's your dat of birth: ");
  
    fgets(buffer, bufferLen, stdin);
  
    sscanf(buffer, "%i/%i/%i", &DOB[0], &DOB[1], &DOB[2]);
  
    printf("day: %i, month: %i, year: %i\n", DOB[0], DOB[1], DOB[2]);
    return 0;
}
```

First we create a buffer. A buffer is an array of a set length that will hold the initial input string. In this example the buffer is 12 characters long (one of those characters is the null character at the end of strings so it will seem a little shorter than it is).

We then print out a prompt to the user to input a date of birth.

We then use the `fgets()` function to read in what the user puts on the command line. It takes the buffer as its first param, the length of the characters to read as its second, and the file it is reading from as the third. C treats the command line as a file called `stdin` so that's what we put here. This is a very safe way of getting input as the user can input as many characters as they like but it will only read the first n characters where n is second parameter we put into the function.

Then we use `sscanf()` to scan the buffer for integers. We assume the user inputs the date as a `dd/mm/yyyy` format which is there the second parameter - the format string - comes from. The rest of the parameters are where we want the function to store the integers. It wants the address of the variables where it needs to store the data.

Lastly we print out the result.

### Errors with fgets
If the buffer used is shorter than the user input, the remaining input will be stored by fgets and then used in subsequent calls of the function. 

This can be solved by looking for a newline character in the string we read, and if we do not find one, we can use `getc()` to read individual characters till we find the newline character.