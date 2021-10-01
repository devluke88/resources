# Basic Commands

### Getting Help Commands

| \# | Command | Description |
| :--- | :--- | :--- |
| 1 | `man [command]` | manual pages explaining a given command |
| 2 | `man -k [search_term]` | option `-k` will look through all man pages to find your term and display to the screen |
| 3 | `info [command]` | similar to `man` command, but more detailed, will print info about a given command |
| 4 | `vim --help` or `vim -h` | `--help` command provides guidance for application use, in this example we use `vim` a single dash \(-\) is used before single-letter options, for example `-h` a double dash \(--\) on the other hand before word options, such as `--help` |

### 

### Navigating Files and Directories

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
| 9 | `ls -R` | recursive listing |
| 10 | `cd [path]` | change directory, if used alone will go to the home directory `~` |
| 11 | `cd ..` | move one level up in the file structure |
| 12 | `cd ../..` | move two levels up in the file structure and so on |
| 13 | `cd /` | move to the root level of the file system |
| 14 | `cd -` | go back to the last location |
| 15 | `cd ~` | go to the user's home directory; you can also use `cd $HOME` |

### 

### Creating and Managing Files/Directories/Links

| \# | Command | Description |
| :--- | :--- | :--- |
| 1 | `touch [file_name]` | create an empty file |
| 2 | `mkdir [directory]` | create a directory |
| 3 | `mkdir -p [directory/subdirectory]` | create nested directories |
| 4 | `rm [file_name]` | remove a file |
| 5 | `rmdir [directory]` | remove the empty directory |
| 6 | `rmdir -p [direcotory/subdirectory]` | delete the set of nested directories, as long as they don't hold non-directory files \(so only containing folders\) |
| 7 | `rm -rf [directory]` | remove a file or directory \(can have files within\) |
| 8 | `cp [source_file] [target_file]` | copy a file |
| 9 | `cp [source_file1] [source_file2] [target_fdir]` | this command allows to copy several files, the last argument has to be the target directory |
| 10 | `cp -R [source_directory] [target_directory]` | used to copy directories and their contents |
| 11 | `cp -i [file_name1] [file_name2]` | confirm overwriting of a file, so when file\_name2 exist we will see a prompt to confirm the action |
| 12 | `mv [file_name1] [file_name2]` | move or rename files |
| 13 | `ln [source_file] [linked_file]` | create a hard link between files |
| 14 | `ln -s [source_file] [linked_file]` | create a symbolic link \(it's like a shortcut\) |



### Other Commands

| \# | Command | Description |
| :--- | :--- | :--- |
| 16 | `echo "text"`  | print text to the screen |
| 17 | `history` | it shows you a list of commands that you've entered since the session started |
| 18 | `export` | view all exported variables |
| 19 | `type [command_name]` | it will describe how its argument would be translated if used as commands; also used to find out whether it is a built-in or external binary file |
|  | `clear` | clear the terminal screen |
|  | `printenv` | print all environmental variables to the screen, they are upper case |
|  | `locate [file_name]` | search for a \[file\_name\], will print the absolute path of all files and directories that matches the search pattern and for which the user has read permission |
|  | `cat, head, tail` |  |
|  | `less` |  |
|  | `more` |  |
|  | `grep` | used for search files containing specifing string, pattern, based on pattern |
|  | `grep -E [regular_expression]` |  |
|  | `sort` |  |
|  | `cut` | command that will extract a text from a field within a file, pull information from file and copy it to anoter places |
|  | `wc -l` |  |
|  | `find` | look for files based on filename, permissions |
|  | ls \| grep file1 | `|`- piping allows to combine two commands |

### Section about redirecting \(2&gt; &gt;&gt; &lt;&lt; &lt;&gt; etc.\)

### Archiving Commands

Options/Flags:  
`-c` create archive  
`-x` extract archive  
`-r` append to an archive  
`-t` list the contents of an archive  
`-f` read from or write to a file  
`-v` show which files are being added to the archive

| \# | Command | Description |
| :--- | :--- | :--- |
| 1 | `tar cf archive.tar [target_file1] [target_file2]` | create the .tar \(tape archive\) |
| 2 | `tar xf archive.tar` | extract the archive |
| 2 | `gzip archive.tar.gz` | Another method that is used for archiving files, size of the archive is much lower -&gt; results in a file with extension: `.gz` |
| 3 | `gunizp archive.tar.gz` | extract archive using GNU unzip command |
| 4 | `bzip2 archive.*` | Another method to zip files - similar to `gzip`, slower but better compression ratios, which means generated file is smaller and results in: `.bz2` format - for example `TestArchive.bz2` , if a file has an extension let's say `.sh` file will be in the following format `filname.sh.bz2` |
| 5 | `bunizp2 archive.bz` | unzip the compressed file |
| 6 | `xz` | .xz |
| 7 | `unxz` |  |
| 8 | `zip` |  |
| 9 | `unzip` |  |

