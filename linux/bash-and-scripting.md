# Bash and Scripting

### Basics

Use the following to define the interpreter to be used by the shell script \(bash in our case\):

```text
#!/bin/bash
```

**Arguments**  
variables that are passed to the script. These are also called parameters  
$0 - the name of the script  
$1 - first parameter from the script  
$2 - second parameter from the script and so on

### Example Script 

See the example script below - script checks the IP with a `ping` command:

```text
#!/bin/bash

$ip=`route -n | grep UG | tr -s " " | cut -f 2 -d " "`

$ping="/bin/ping"

echo "Checking to se if $ip address is up..."

$ping -c 5 $ip
```

### If Statements\*

```text
if [ <condition> ]
then
  <command>
fi
```

See the list of available conditions below:   
!\[expression\] - the expression is false  
-n \[string\]    - the length of the string is greater than zero  
-z \[string\]    - the length of the string is zero  
string1 = string2    - string is equal to sting2  
string1 != string2    - string is not equal to sting2  
integer1 -eq integer2    - integer1 is equal integer2  
integer1 -gt integer2    - integer1 is greater than integer2  
integer1 -lt integer2    - integer1 is less than integer2  
-d \[file\]    - the file exists and is a directory  
-e \[file\]    - the file exists  
-r \[file\]    - the file exists, and the read permission is granted  
-s \[file\]    - the file exists, and its size is greater than zero  
-w \[file\]    - the file exists, and the write permission is granted  
-x \[file\]    - the file exists, and the execute permission is granted  
  
**\*** This section was copied from the Linux Academy course: **LPI Linux Essentials Certification** created by **Michael Christian** -- you can find it [here](https://learn.acloud.guru/course/87e08bad-9655-4a7c-9f07-5dd44149b837/overview).  


### For Loops

```text
for i in list;
    do <command>;
done
```



### While Loops

```text
while [condition]; do
    <command>
done
```

### 

### Case Statements

```text
case [expression] in
    PATTERN_1)
    STATEMENTS
    ;;

  PATTERN_2)
    STATEMENTS
    ;;

  PATTERN_N)
    STATEMENTS
    ;;

  *)
    echo -n "unknown"
    ;;
esac
```





