## Navigation
`h j k l` are used to move around.
```
      ^
      k              Hint:  The h key is at the left and moves left.
< h       l >               The l key is at the right and moves right.
      j                     The j key looks like a down arrow.
      v
```
`PgDn` - exactly a whole page down
`PgUp` - exactly a whole page up

#### Cursor
Using a [[#Motions|motion]] on its own will move the cursor instead of performing an action:
`2w` - moves the cursor to the start of the word 2 words forward
`0` - moves the cursor to the start of the line

`CTRL-g` - show current line and other details about location in file
`gg` - move to the start of the file
`G` - move to the end of the file
`133G` - move you to line 133 (replace 133 with any line number)

`%` - if the cursor is on a bracket, then it will take you to the matching bracket (ie the opening or closing bracket of that pair)

#### Searching
`/phraaase` - type `/` followed by the phrase you want to search for
Once you have searched for a phrase use `n` to go to the next place the phrase is found, and `N` to go to the previous one.
To initially search backwards, type `?` instead of`/`.

`CRTL-o` - go back to where you came from
`CTRL-i` - go forward

#### Selecting text
`v` - starts selection mode
Then use any cursor movement commands to manipulate the selection


## 'External' commands
`:q!` - exit editor discarding changes
`:wq` - exit and save changes

`:!{command}` - execute external command. It will take you out the vim window, show the command output and then you can hit enter to re-enter vim again.

`:w filename.txt` - creates a copy of the file you are editing at its current state and stores it at 'filename.txt'
*If you currently have a section of text selected, vim will instead save that to the new file, not the whole current file you are working on*

`:r filename.txt` - (read) inserts the contents of 'filename.txt' and inserts it BELOW the current line
`:r !{command}` - inserts the output of the command into the file


## Text editing
**Modes**
`i` - put you into insert mode so you can write text like normal
`a` - (append) puts you in insert mode but the character AFTER the one you currently have selected
`A` - (append) automatically jump you to the end of the line and put you into insert mode. (Capital A)
`o` - opens up a newline below the cursor and puts you in insert mode
`O` - opens up a newline above the cursor and puts you in insert mode

#### Text manipulation
`y{motion}` - (yank) copy
`d{motion}` - delete
`p` - paste. Will paste entire lines on the line below.
*Deleting will 'cut' any text it removes which can then be pasted by `p`*

**Single Character**
`x` - delete the character underneath the cursor
`r` - replace the character underneath the cursor with the next typed character
`R` - keep replacing characters until you press `esc`
`c{motion}` - deletes the amount the motion specifies and then puts you into insert mode

**Undo/Redo**
`u` - undo last command
`U` - undoes all changes on the current line
`CTRL-r` - redo

#### Substitute
`:s/old/new/g` - substitute 'new' for 'old' for every occurrence in the line
`:s/old/new` - substitute 'new' for 'old' only for the first occurrence of the line (not from current cursor position)
`:12,14s/old/new/g` - replace every occurrence of 'old' with 'new' between lines 12 and 14
`:%s/old/new/g` - replace every occurrence of 'old' with 'new' in the whole file
`:%s/old/new/gc` - replace every occurrence of 'old' with 'new' in the whole file but prompt each time to ask if you want to replace or not
**/c**
If you use the `/c` flag you get options:
- `y` - yes for currently selected
- `n` - no for currently selected
- `a` - yes for all
- `q` - (quit) no for all
- `l` - (last) yes for current selected then quit 
- `CTRL-e` - move page down a line
- `CTRL-y` - move page up a line

#### Set Options
*Used to effect [[#Substitute]] and [[#Searching|Search]] cases.*
`:set ic` - ignore case. Searches and substitutions will now ignore case
`:set hsl` - (highlight search) highlight all found terms for search
`:set is` - (inclusive search) find the words as you type
`/word\c` - ignores case for just this search

Preface any of these with `no` to remove the option: `:set noic`, `:set nohls`, `:set nois`


## Motions
`w` - until the start of the next word (remove space)
`e` - to the end of the current word (keeps space)
`$` - to the end of the line
`0` - to the beginning of the line
*repeat operator again* - does the operation for the whole line eg. `dd` deletes the whole line
*number before double operator* - performs the action for # lines eg. `2dd` deletes 2 whole lines
``
**Adding a number before a motion will repeat it that many times**
`d2w` - delete until the start of the 2nd word in front

## Customisation
`:set number` - adds line numbers

Main way to customise is to edit the `~/.vimrc` file. An example file can be found at `$VIMRUNTIME/vimrc_example.vim`. Read this file into the `.vimrc` file to get started.

## Help
- `:help` - provides a help page for vim
- At terminal type `vimtutor` and it will come up with a full tutorial that goes through all of the commands above.
- When typing a command, if you start it and press `CTRL-d` vim will show you all commands that start with what you have typed
- You can also use tab to autocomplete vim commands, similar to at the command line
