## Opening a file

```C
char *filename = "file.txt";
FILE *fp_inputFile = fopen(filename, "r");
```

#### Opening in a separate function
You need to send a pointer to a pointer (I don't fully understand why yet...)
```c
int openFile(char *filename, FILE **file, char *mode) {
    *file = fopen(filename, mode);
    return 0;
}

int main() {
	FILE *inputFile;
    openFile(inputFileName, &inputFile, "r");
}
```

## Reading a file

```C
char lineBuffer[25];
char *line = fgets(lineBuffer, 25, fp_inputFile);
```

## Binary files
```C
void binaryWrite(void)
{
    char *word = "This is a word";
    int num[] = {20, 21, 22};
    int num2[3];    

    FILE *f = fopen("testfile.ebu", "wb");
    fwrite(num, sizeof(num[0]), 3, f);
    fclose(f);

    FILE *f2 = fopen("testfile.ebu", "rb");
    fread(num2, sizeof(num[0]), 3, f2);
    for (int i = 0; i < 3; i++) {

        printf("%d\n", num2[i]);

    }
    fclose(f2);
}
```