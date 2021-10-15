# Bash Shell
<p style= "text-align: right"><i>Created 16/09/2021</i></p>

A collection of bash shell commands.

- `cat`: concatenate one or more files contents to `stdout`
- `cd`: change directory
- `chmod`: change permissions on a file or folder.
- `compgen`: show available commands, aliases, functions. Use `-c` to input the beginning of a command name and see possible completions.
- `cp`: copy files or directories (recursively with `-r`, interactively with `-i`)
-  `echo`: print something in `stdout`
- `grep`: search text in a file or (long) string. Useful options: `-n` to print number lines along with results of search; `-i` to pass files as targets of the search.
- `head`: print first few lines of a file (see `tail`)
- `history`: print last bash commands
- `less`: show the content of a file in a read-only window. Use `-e` to quit at end of file and `-n` to show line numbers.
- `ls`: list directory contents
- `locate`:  search a file or directory.
- `man`: show manual of standard utilities
- `mkdir`: create one or more directories
- `mv`: rename or move (edit absolute path of) files. Useful option: `-i`, interactive.
- `pwd`: print working directory
- `rmdir`: remove an empty directory. Useful options: `-p` remove also parents if empty.
- `tail`: print last few lines of a file (see `head`)  
- `touch`: create new file(s) or modify access or modification time of files
- `wc`: compute statistics about a file's content
- `>`: redirect output of preceding command into a file 
- `|`: pass output of preceding command to following command

***

## Writing scripts
- to check conditions `test` and `[ <exp> ]` are equivalent, old ways. The new implementation of this is `[[ <exp> ]]` which is equivalent and more powerful. [-source](http://mywiki.wooledge.org/BashFAQ/031).
- [regex basics](https://linuxtechlab.com/bash-scripting-learn-use-regex-basics/)