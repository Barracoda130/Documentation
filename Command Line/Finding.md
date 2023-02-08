## Grep
```shell
grep 'word' filename.txt
``` 
Returns every line that contains 'word' inside file 'filename.txt'. You can put as many filenames as you would like after the first and it will search them all.

```shell
grep -R 'word'
# OR
grep -r 'word'
```
Looks for the word 'word' inside every file in the current directory and all subdirectories

```shell
cat filename.txt | grep 'word'
```
You can also pipe command outputs into grep.

```shell
grep -E -w 'word1|word2' file.txt
```
The `-E` turns it into egrep - a depreciated version of grep - which searches using extended regular expressions. This will search for both 'word1' and 'word2' separately.

#### Flags
`-i` - Ignore case of the letters
`-c` - the number of times the phrase appears
`-h` - removes filenames showing where the word was found
`-w` - search for words only
`-n` - show the line number where the word was found
`-v` - invert match - prints every line NOT containing the phrase
`-B 2` - shows the 2 lines before the word found as well as the line it is found on
`-A 2` - shows the 2 lines after the word found as well as the line it is found on

#### Notes
- Will look for exact strings, so you can search for letters inside words



