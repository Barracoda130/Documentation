## Phony
`.PHONY` is used to specify commands that don't require a file that matches the name of the function when they finish. 
For example, if I have a function defined `test: test.o`, make will expect it to produce a file called `test` once it finishes running and it will throw an error if that doesn't happen.
`.PHONY test` tells make that the `test` function doesn't create a test file.

Make has some default `.PHONY` targets like `clean` and `all` but it is good practice at the end of your makefile to specify all the non-file targets.

### Default build target
`.DEFAULT_GOAL function` is used to say which function runs by default if you only type `make` into the command line.