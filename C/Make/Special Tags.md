### Preventing command echo
Normally with make, when it runs a command, it will output that command to the terminal as it runs it. To stop that, we can put `@` at the beginning of that line, and it won't show in the terminal.
For example:
```shell
clean:
    @$(RM) -rf $(BUILDDIR)
```

### Ignoring command errors
Normally, if any of the commands throw an error, make will stop. In order to prevent that we can use `-` before the command.
For example:
```shell
directories:
    -mkdir -p $(TARGETDIR)
    -mkdir -p $(BUILDDIR)
```
It can be very useful in scenarios like this, as if the directory already exists, windows will throw an error saying it can't make the directory, but we don't care about that as we just wanted to make sure the directory was there.