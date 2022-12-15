## Opening a file

```C
char *filename = "file.txt";
FILE *fp_inputFile = fopen(filename, "r");
```

## Reading a file

```C
char lineBuffer[25];
char *line = fgets(lineBuffer, 25, fp_inputFile);
```
