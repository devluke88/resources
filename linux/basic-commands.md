# Basic Commands

### Getting Help Commands

| # | Command                  | Description                                                                                                                                                                                                                                                                                       |
| - | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | `man [command]`          | manual pages explaining a given command                                                                                                                                                                                                                                                           |
| 2 | `man -k [search_term]`   | option `-k` will look through all man pages to find your term and display to the screen                                                                                                                                                                                                           |
| 3 | `info [command]`         | similar to `man` command, but more detailed, will print info about a given command                                                                                                                                                                                                                |
| 4 | `vim --help` or `vim -h` | <p><code>--help</code> command provides guidance for application use, in this example we use <code>vim</code><br>a single dash (-) is used before single-letter options, for example <code>-h</code><br>a double dash (--) on the other hand before word options, such as <code>--help</code></p> |

###

### Navigating Files and Directories

| #  | Command     | Description                                                                                                                                            |
| -- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1  | `pwd`       | _present working directory_ - shows you a current location within the directory structure                                                              |
| 2  | `ls`        | _list_ command - list the content of the directory                                                                                                     |
| 3  | `ls -a`     | Show visible and hidden files and directories, option `-a` is `--all`                                                                                  |
| 4  | `ls -l`     | `-l` option stands for _long_ - give you more information about the files and directories - permissions, owner, size, and when they were last modified |
| 5  | `ls -lh`    | this option shows you human-readable sizes, for example, 5M or 1.9K                                                                                    |
| 6  | `ls -lhS`   | `-S` flag will sort the results by file size, default is the name                                                                                      |
| 7  | `ls -lt`    | sort by last modified time `-t`                                                                                                                        |
| 8  | `ls -lr`    | reverse sort, using the `-r` flag                                                                                                                      |
| 9  | `ls -R`     | recursive listing                                                                                                                                      |
| 10 | `cd [path]` | change directory, if used alone will go to the home directory `~`                                                                                      |
| 11 | `cd ..`     | move one level up in the file structure                                                                                                                |
| 12 | `cd ../..`  | move two levels up in the file structure and so on                                                                                                     |
| 13 | `cd /`      | move to the root level of the file system                                                                                                              |
| 14 | `cd -`      | go back to the last location                                                                                                                           |
| 15 | `cd ~`      | go to the user's home directory; you can also use `cd $HOME`                                                                                           |

###

### Creating and Managing Files/Directories/Links

| #  | Command                                          | Description                                                                                                       |
| -- | ------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| 1  | `touch [file_name]`                              | create an empty file                                                                                              |
| 2  | `mkdir [directory]`                              | create a directory                                                                                                |
| 3  | `mkdir -p [directory/subdirectory]`              | create nested directories                                                                                         |
| 4  | `rm [file_name]`                                 | remove a file                                                                                                     |
| 5  | `rmdir [directory]`                              | remove the empty directory                                                                                        |
| 6  | `rmdir -p [direcotory/subdirectory]`             | delete the set of nested directories, as long as they don't hold non-directory files (so only containing folders) |
| 7  | `rm -rf [directory]`                             | remove a file or directory (can have files within)                                                                |
| 8  | `cp [source_file] [target_file]`                 | copy a file                                                                                                       |
| 9  | `cp [source_file1] [source_file2] [target_fdir]` | this command allows to copy several files, the last argument has to be the target directory                       |
| 10 | `cp -R [source_directory] [target_directory]`    | used to copy directories and their contents                                                                       |
| 11 | `cp -i [file_name1] [file_name2]`                | confirm overwriting of a file, so when file\_name2 exist we will see a prompt to confirm the action               |
| 12 | `mv [file_name1] [file_name2]`                   | move or rename files                                                                                              |
| 13 | `ln [source_file] [linked_file]`                 | create a hard link between files                                                                                  |
| 14 | `ln -s [source_file] [linked_file]`              | create a symbolic link (it's like a shortcut)                                                                     |



### Searching, Extracting and Displaying Data

| #  | Command                                                | Description                                                                                                                                                                                                              |
| -- | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1  | `echo "text"`                                          | print "text " string to the screen                                                                                                                                                                                       |
| 2  | `locate [file_name]`                                   | search for a \[file\_name], will print the absolute path of all files and directories that matches the search pattern and for which the user has read permission                                                         |
| 3  | `grep`                                                 | used for search files containing specifying string, pattern, based on pattern                                                                                                                                            |
| 4  | `grep -E [regular_expression]`                         | search to match pattern using regex                                                                                                                                                                                      |
| 5  | `grep "example" [files]`                               | search for "example" string in files, which you can replace it with your pattern                                                                                                                                         |
| 6  | `grep -n [searching_phrase] RREADME.md`                | searching with `-n` flag will display numbers as a part of the output                                                                                                                                                    |
| 7  | `grep -R "example" [directory]`                        | search recursively through the directory, and it all subdirectories                                                                                                                                                      |
| 8  | `grep -v "example"`                                    | search for everything apart from "example"                                                                                                                                                                               |
| 9  | `ls \| grep [file1]`                                   | `\|`- piping allows combining two or more commands, in this case, we use grep to look for file1 in ls output                                                                                                             |
| 10 | `ls > file1`                                           | send the output to `file1` (save the output in this file)                                                                                                                                                                |
| 11 | `ls >> file1`                                          | append output to a `file1`                                                                                                                                                                                               |
| 12 | `grep test < file1`                                    | read input from a `file1`                                                                                                                                                                                                |
| 13 | `find [path_to_search] [flag] [pattern_to+search_for]` | search for a file                                                                                                                                                                                                        |
| 14 | `find / -name test.txt`                                | search in _home directory_ for a file named _test.txt_                                                                                                                                                                   |
| 15 | `find . \( -name \*.png -or -name \*.jpg \) -type f`   | search the current directory for files whose name either end in _.png_ or _.jpg_ format                                                                                                                                  |
| 16 | `cat [file_name]`                                      | display content of a file in the terminal                                                                                                                                                                                |
| 17 | `more [file_name]`                                     | output the contents of a file, good when you need to look into big files, you can scroll the page                                                                                                                        |
| 18 | `less [file`\_`name]`                                  | similar to `more` command, it used to read the contents of a file, one page at the time                                                                                                                                  |
| 19 | `head [file_name]`                                     | it outputs the first 10 lines of a file to the screen                                                                                                                                                                    |
| 20 | `tail [file_name]`                                     | it outputs the last 10 lines of a file to the screen                                                                                                                                                                     |
| 21 | `tail -n 5 [path/file_name]`                           | output the last 5 lines of a file                                                                                                                                                                                        |
| 22 | `sed s/mysql/MYSQL/g /etc/filename.conf > snort2.conf` | `sed` command is used to find and replace keywords or phrases - in the example, we are looking for `mysql` (s used to search) and replacing it with `MySQL` (g means replace globally - all occurrences of it in a file) |
| 23 | `sed s/mysql/MYSQL/ /etc/filename.conf > snort2.conf`  | in the example, only the first occurrence of `mysql` will be replaced with `MySQL`                                                                                                                                       |
| 24 | `sed s/mysql/MYSQL/2 /etc/filename.conf > snort2.conf` | this command affects only the second occurence of `mysql`                                                                                                                                                                |



### Networking Commands

| #     | Command                  | Description                                                                            |
| ----- | ------------------------ | -------------------------------------------------------------------------------------- |
| **1** | `ping [ip_address]`      | ping host and output results                                                           |
| 2     | `ping -c 5 [ip_address]` | do 5 pings                                                                             |
| 3     | `whois [domain_name]`    | get whois info for a given domain                                                      |
| 4     | `dig [domain_name]`      | DNS lookup utility, get DNS info for a given domain                                    |
| 5     | `dig -x [addr]`          | DNS reverse lookup                                                                     |
| 6     | `host [domain_name]`     | DNS lookup utility, get DNS info for a given domain                                    |
| 7     | `cat /etc/reslov.conf`   | shows which configuration file is used to determine which hosts to use for DNS queries |
| 8     | `/etc/hosts`             | used for statically mapping IP addresses to hostnames                                  |
| 9     | `ip route show`          | shows the current routing table                                                        |
| 10    | `ip addr show`           | show the current IP addresses                                                          |
| 11    | `ifconfig`               | view and change the interface configuration; for wireless interface use `iwconfig`     |
| 12    | `traceroute google.com`  | shows you all the hops/routes with IP addresses your packets travel                    |
| 13    | `wget [url]`             | it allows you to download the zipped module                                            |
| 14    | `wget -c [file]`         | continue a stopped download                                                            |
| 15    | `netstat`                | view listing services and active connections                                           |
| 16    | `ss`                     | similar to `netstat` - list out all the network (socket) connections on a system       |
| 17    | `curl [url]`             | make an HTTP request to a given server and print its response in the terminal console  |
| 18    | `curl -i [url]`          | gives you more information about the response                                          |

###

### SSH Access Commands

| #     | Command                           | Description                                                                                  |
| ----- | --------------------------------- | -------------------------------------------------------------------------------------------- |
| **1** | `sudo apt install openssh-server` | install ssh service                                                                          |
| 2     | `sudo systemctl enable ssh`       | enable ssh service                                                                           |
| 3     | `sudo systemctl start ssh`        | start ssh service on the device                                                              |
| 4     | `sudo systemctl status ssh`       | show the status of the ssh service (you can also _restart_, _stop_ or _disable_ the service) |
| 5     | `ssh user@host`                   | connect to the _host_ as _user_                                                              |
| 6     | `ssh -p [port] user@host`         | connect to the _host_ as _user_ on port                                                      |
| 7     | `sudo ufw allow ssh`              | you might need to configure the firewall to open port 22 on Ubuntu                           |
| 8     | `sudo ufw enable`                 | enable `ufw`                                                                                 |
| 9     | `sudo ufw status`                 | check status of `ufw`                                                                        |
| 10    | `ssh-copy-id vivek@power9`        | copy and install the public key so you can use passwordless login                            |

###

### Process Management Commands

| #     | Command                         | Description                                                                                                                                                                  |
| ----- | ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1** | `ps`                            | list the processes started by logged in user                                                                                                                                 |
| 2     | `ps aux`                        | display all processes running on the system                                                                                                                                  |
| 3     | `top`                           | display top running processes, based on CPU and memory usage                                                                                                                 |
| 4     | `kill [pid]`                    | kill a process by providing its PID                                                                                                                                          |
| 5     | `nice -n -10 /bin/slowprocess`  | this command gives higher priority (scale from -20 to 19, where -20 is the most priority) to the `slowprocess`                                                               |
| 6     | `renice 20 6996`                | this command set the priority to a given process; in the example, we set priority 20 (you can set also a negative number which will give higher priority) for a process 6996 |



### System Info Commands

| #     | Command                                                                  | Description                                                                                                                                                                                                                                                                                                                    |
| ----- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1** | `whoami`                                                                 | show which user you're logged in as                                                                                                                                                                                                                                                                                            |
| 2     | `last`                                                                   | show a listing of last logged in users                                                                                                                                                                                                                                                                                         |
| 3     | `who`                                                                    | display who is currently logged in                                                                                                                                                                                                                                                                                             |
| 4     | `w`                                                                      | used to show who is logged in and what they are doing (login name, the tty name, the remote host, login time, idle time, JCPU (time used by all processes), PCPU (time used by the current process), WHAT - the command line of their current process                                                                          |
| 4     | `date`                                                                   | print the system date                                                                                                                                                                                                                                                                                                          |
| 5     | `cal`                                                                    | show calendar                                                                                                                                                                                                                                                                                                                  |
| 6     | `df`                                                                     | show system disk space usage                                                                                                                                                                                                                                                                                                   |
| 7     | `du`                                                                     | show estimate directory space usage                                                                                                                                                                                                                                                                                            |
| 8     | `free`                                                                   | show memory and swap usage                                                                                                                                                                                                                                                                                                     |
| 9     | `cat /proc/cpuinfo`                                                      | show the cpu information                                                                                                                                                                                                                                                                                                       |
| 10    | `cat /proc/meminfo`                                                      | show the memory info                                                                                                                                                                                                                                                                                                           |
| 11    | `whereis [app_name]`                                                     | show location of a given application                                                                                                                                                                                                                                                                                           |
| 12    | `which [app_name]`                                                       | return the path of a file which will be executed for a given application                                                                                                                                                                                                                                                       |
| 13    | `uname -a`                                                               | show kernel information                                                                                                                                                                                                                                                                                                        |
| 14    | `dmesg`                                                                  | print all messages from the kernel ring buffer                                                                                                                                                                                                                                                                                 |
| 15    | `hostnamectl`                                                            | display info about the hostname, OS, kernel, architecture, etc.                                                                                                                                                                                                                                                                |
| 16    | `lsb_release -a`                                                         | show basic info about OS and its distribution                                                                                                                                                                                                                                                                                  |
| 17    | `fdisk -l`                                                               | using `fdisk` utility with `-l` switch will list all the partitions pf all drives with their capacity; requires root privileges                                                                                                                                                                                                |
| 18    | `lsblk`                                                                  | useful command that stands for _list block_ and lists some basic information about each block device listed in `/dev`. Similar to `fdisk -l` with the difference that will also display devices with multiple partitions in a tree, showing each device with its partitons as branches; doesn't require root privileges to run |
| 19    | `mount /dev/sdb1 /mnt`                                                   | this is used to mount the new hard drive _sdb1_ at `/mnt` directory                                                                                                                                                                                                                                                            |
| 20    | `mount /dev/sdc1 /media`                                                 | this command will mount your USB drive                                                                                                                                                                                                                                                                                         |
| 21    | `umount /dev/sdb1`                                                       | unmount your drive (command spelt `umount` without _n_)                                                                                                                                                                                                                                                                        |
| 22    | `fsck`                                                                   | check and repair Linux filesystem errors                                                                                                                                                                                                                                                                                       |
| 23    | <p><code>umount /dev/sdb1 \</code><br><code>fsck -p /dev/sdb1</code></p> | to use `fsck` command you need first unmount your device and then run`fsck` command. `-p` switch will automatically repair any problems with the device                                                                                                                                                                        |
| 24    | `id [user_name]`                                                         | show info about user and his groups                                                                                                                                                                                                                                                                                            |



### File/User Permissions Commands

| #     | Command                                              | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ----- | ---------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1** | `chmod 774 [file_name]`                              | <p>set the permission subsequently for the owner, group, all users (others) to a given file<br>Available permissions:<br>-<code>r</code> (read - octal value: 4)<br>-<code>w</code> (write - octal value: 2)<br>-<code>x</code> (execute - octal value: 1)<br>in the example, the owner and group get all permissions (4+2+1), and all users only read access (4).<br>When you create or download a file - Linux automatically assigns base permissions - 666 for files and 777 for directories</p> |
| 2     | `chmod u-w [file_name]`                              | removes (-) the write (w) permission from hashcat.hcsta for the user/owner (u)                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 3     | `chmod u+x,o+x [file_name]`                          | <p>you can add (+) the executable (x) permission for a user (u) and other users (o). UGO syntax use:<br>- user/owner (u)<br>- groups (g)<br>- others (o)<br>You can use three operators to set permissions:<br>- Remove permission with <code>-</code><br>- Add a premission wiht <code>+</code><br>- Set permission with <code>=</code><br>Permissions are comma-separeted (<code>,</code>) and there is no space</p>                                                                              |
| 4     | `chown [user] [file_name]`                           | change a file's user ownership                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 5     | `chown :group_name [file_name]`                      | change a file's group ownership                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 6     | `chown user:group file1`                             | changes a file's user and group ownership                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| 7     | `chgrp [groupname] [filename]`                       | change group of a given file                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| 8     | `useradd -m [user_name]`                             | create a user and its directory                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 9     | `sudo passwd [user_name]`                            | change user password                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 10    | `sudo -l passwd [user_name]`                         | lock a user account                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| 11    | `userdel [user_name]`                                | delete a user                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 12    | `sudo usermod -a -G developers,employes [user_name]` | add a user to groups: developers and employees  (done with `usermod` - as the user already exist so we need to modify his permissions                                                                                                                                                                                                                                                                                                                                                               |

###

### Installation Commands

| # | Command                          | Description                                                               |
| - | -------------------------------- | ------------------------------------------------------------------------- |
| 1 | `apt-get install [package_name]` | install a given package on  Ubuntu                                        |
| 2 | `apt-cache search keyword`       | check if a package is available in your repository                        |
| 3 | `apt-get remove [package_name]`  | removes a package from your repo, but keeps the configuration files       |
| 4 | `apt-get purge [package_name]`   | removes package and configuration files from your repo                    |
| 5 | `apt-get update`                 | update your system packages                                               |
| 6 | `apt-get upgrade`                | upgrade existing packages on your system                                  |
| 7 | `yum install [package_name]`     | install a package using `yum` - used in the different distro, like CentOS |

###

### Archiving Commands

**Options/Flags:**\
`-c` create archive\
`-x` extract archive\
`-r` append to an archive\
`-t` list the contents of an archive\
`-f` read from or write to a file\
`-v` show which files are being added to the archive

| # | Command                                            | Description                                                                                                                                                                                                                                                                                   |
| - | -------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | `tar cf archive.tar [target_file1] [target_file2]` | create the .tar (tape archive)                                                                                                                                                                                                                                                                |
| 2 | `tar xf archive.tar`                               | extract the archive                                                                                                                                                                                                                                                                           |
| 2 | `gzip archive.tar.gz`                              | Another method that is used for archiving files, size of the archive is much lower -> results in a file with extension: `.gz`                                                                                                                                                                 |
| 3 | `gunizp archive.tar.gz`                            | extract archive using GNU unzip command; alternatively, you can use `gz -d file.gz`                                                                                                                                                                                                           |
| 4 | `bzip2 archive.*`                                  | Another method to zip files - similar to `gzip`, slower but better compression ratios, which means generated file is smaller and results in: `.bz2` format - for example `TestArchive.bz2` , if a file has an extension let's say `.sh` file will be in the following format `filname.sh.bz2` |
| 5 | `bunizp2 archive.bz`                               | unzip the compressed file                                                                                                                                                                                                                                                                     |
| 6 | `xz -z [target_file]`                              | zip file in the `.xz` format, `-z` or `--compress` usually used; this utility offers the best compression                                                                                                                                                                                     |
| 7 | `unxz [archive_name]`                              | decompress a file, you can also use `xz -d [archive_name]`                                                                                                                                                                                                                                    |
| 8 | `zip archive_name.zip [file1] [file2]`             | another command to archive files                                                                                                                                                                                                                                                              |
| 9 | `unzip`                                            | used to unzip files while using `zip` command                                                                                                                                                                                                                                                 |



### Other Commands

| #     | Command                    | Description                                                                                                                                                                                                                                                        |
| ----- | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1** | `history`                  | it shows you a list of commands that you've entered since the session started                                                                                                                                                                                      |
| 2     | `export`                   | view all exported variables, use `export VARIABLENAME`to export VARIABLENAME                                                                                                                                                                                       |
| 3     | `printenv`                 | print all environment variables to the screen, they are upper case                                                                                                                                                                                                 |
| 4     | `type [command_name]`      | it will describe how its argument would be translated if used as commands; also used to find out whether it is a built-in or external binary file                                                                                                                  |
| 5     | `clear`                    | clear the terminal screen                                                                                                                                                                                                                                          |
| 6     | `sort [fil_name]`          | sort the contents of the file and display it on the screen                                                                                                                                                                                                         |
| 7     | `cut -b 1-3,5-7 test.txt`  | the command that will extract a text from a field within a file, pull information from a file and write the result to standard output; this particular example is using `-b` flag (byte) to extract specific bytes, a list with ranges 1-3,5-7                     |
| 8     | `wc -l`                    | <p>word count command, used to find a number of newline count, word count, byte and character count; options:</p><ul><li><code>-l</code> - print new lines count</li><li><code>-c</code> - print bytes count</li><li><code>-m</code> - print chars count</li></ul> |

###

### Keyboard Shortcuts

| #     | Command          | Description   |
| ----- | ---------------- | ------------- |
| **1** | `ctrl + alt + t` | open terminal |
|       |                  |               |



**More commands can be found in this repo:** [https://github.com/devluke88/linux-repo](https://github.com/devluke88/linux-repo)
