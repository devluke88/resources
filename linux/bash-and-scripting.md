# Bash and Scripting

Start your script with:

```text
#!/bin/bash
```

**Arguments**  
variables that are passed to the script. These are also called parameteres  
$0 - name of the script  
$1 - first parameter from the script  
$2 - second parameter from the script and so on

Example script checking IP with ping command:

```text
#!/bin/bash

$ip=`route -n | grep UG | tr -s " " | cut -f 2 -d " "`

$ping="/bin/ping"

echo "Checking to se if $ip address is up..."

$ping -c 5 $ip
```



