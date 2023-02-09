## `ls` Colour output
To remove the coloured boxes around directories:
1. Copy the dircolors settings
```bash
dircolors -p > ~/.dircolors
```
`dircolor -p` prints the current config and `>` redirects the output to the given file.
2. Now open the file in an editor and find the following line:
```bash
OTHER_WRITABLE 34;42 # dir that is other-writable (o+w) and not sticky
```
3. Change the number `42` (denoting green background) to `01` (no background)