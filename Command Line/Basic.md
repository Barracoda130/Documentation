#### cat
Joins and prints input (mainly files)

#### sort
Sorts lines alphabetically by default or numerically

#### cut
Split lines of text based on character provided. Can only split at 1 character.
```shell
cut -d ',' -f 2
```
This will split the line(s) around the comma and give you the second half

#### sed
Stream Editor. Can be used to perform basic text transformations.
```shell
sed '50q;d'
```
This will find the 50th line of the input.

#### wc
Count things inside a file (number of lines, words, bytes etc.)
```shell
wv -w
```
Number of words in a file.