# Basic Commands

See the list of basics commands below:

| \# | Command | Description |
| :--- | :--- | :--- |
| 1 | `pwd` | _present working directory_ - shows you a current location within the directory structure |
| 2 | `ls` | _list_ command - list the content of the directory |
| 3 | `ls -a` | Show visible and hidden files and directories, option `-a` is `--all` |
| 4 | `ls -l`  | `-l` option stands for _long_ - give you more information about the files and directories - permissions, owner, size, and when they were last modified |
| 5 | `ls -lh` | this option shows you human-readable sizes, for example, 5M or 1.9K |
| 6 | `ls -lhS` | `-S` flag will sort the results by file size, default is the name |
| 7 | `ls -lt` | sort by last modified time `-t` |
| 8 | `ls -lr` | reverse sort, using the `-r` flag |
|  | `ls -R` | recursive listing |
| 9 | `cd [path]` | change directory, if used alone will go to the home directory `~` |
| 10 | `cd ..` | move one level up in the file structure |
| 11 | `cd ../..` | move two levels up in the file structure and so on |
| 12 | `cd /` | move to the root level of the file system |
| 13 | `man [command]` | manual pages explaining a given command |
|  | `man -k [search_term]` | option `-k` will look through all man pages to find your term and display to the screen |
| 14 | `info [command]` | similar to `man` command, but more detailed, will print info about a given command |
| 15 | `mkdir` | create a folder |
| 16 | `echo "text"`  | print text to the screen |
| 17 | `history` | it shows you a list of commands that you've entered since the session started |
| 18 | `export` | view all exported variables |
| 19 | `type [command_name]` | it will describe how its argument would be translated if used as commands; also used to find out whether it is a built-in or external binary file |
|  | `rmdir` | remove the empty directory |
|  | `rmdir -p filename` | delete the set of nested directories, as long as they don't hold non-directory files \(so only cotaining folders\) |
|  | `touch [file_name]` | create an empty file |
|  | `rm` | remove a file |
|  | `rm -rf` | remove a file or directory \(can have files within\) |
|  | `clear` | clear the terminal screen |
|  | `printenv` | print all environmental variables to the screen, they are upper case |
|  | `locate [file_name]` | search for a \[file\_name\], will print the absolute path of all files and directories that matches the search pattern and for which the user has read permission |
|  | `cp file1 file1_copy` | copy files |
|  | `cp -r foldername foldername2` | used to copy directories and its contents, you can also use `-a` switch |
|  | `mv file1 file2` | move or rename files |
|  | `ln [origname] [linkname]` | create a hard link |
|  | `ln -s [origname] [linkname]` | create a soft/symbolic link |
|  | `cat, head, tail` |  |
|  | `less` |  |
|  | `more` |  |
|  | `grep` | used for search files containing specifing string, pattern, based on pattern |
|  | `grep -E [regular_expression]` |  |
|  | `sort` |  |
|  | `cut` | command that will extract a text from a field within a file, pull information from file and copy it to anoter places |
|  | `wc -l` |  |
|  | `find` | look for files based on filename, permissions |



Archive commands

| \# | Command | Description |
| :--- | :--- | :--- |
| 1 | `tar` | .tar |
| 2 | `gzip` | .gz |
| 3 | `gunizp` |  |
| 4 | `bzip2` | .bz2 |
|  | `bunizp2` |  |
| 5 | `xz` | .xz |
| 6 | `unxz` |  |
| 7 | `zip` |  |
| 8 | `unzip` |  |

