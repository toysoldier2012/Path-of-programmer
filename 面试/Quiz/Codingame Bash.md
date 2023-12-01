
# QCM

### Sed with templates
Problem solving (40 pts)

Select all the correct statements regarding the following code. 

```bash
#!/bin/bash

g() {
    local m=100 
    [ $# -eq 1 ] && m=$1
    echo $((RANDOM%m))
}

ifile=items
in=$(cat $ifile | wc -l)
n=$(g ${in})
np=$((n+1))
item=$(sed -n "$np"p $ifile)

sed -e 's/ITEM/'"$item"'/g' template.md > output.md
```

- It uses an array
- It gets a random line from the `items` file
- It replaces the text `ITEM` with the value of the `item` variable using the `template.md` file
- It uses command substitution several times
- It uses command substitution once

  
### If and read
Language knowledge (20 pts)

Consider the following code:

```bash
#!/bin/bash

config_file="/etc/dhcp/hosts.config"

echo -e "Hit 'y' to continue"
read -rsn1 check

if [ "$check" != "y" ]
then
    echo "Exiting..."
    exit 1
fi


(cat << EOT
host 320005-windows7-client {
  hardware ethernet 02:00:00:32:00:05;
  fixed-address 192.168.32.5;
  option host-name "320005-windows7-client";
}

host 320006-debian10-client {
  hardware ethernet 02:00:00:32:00:06;
  fixed-address 192.168.32.6;
  option host-name "320006-debian10-client";
}
EOT
) > "$config_file"
```

Select all the correct statements regarding this code. 

- It automatically overwrites the configuration file
- It overwrites the configuration file after confirmation
- It produces a syntax error
- It creates a configuration file after confirmation
- It automatically creates a new configuration file

### IFS and input redirection
Language knowledge (40 pts)

Select all the correct statements regarding the following code. 

```bash
#!/bin/bash

while IFS=":" read -r user _ uid _
do
    echo "$user -- $uid"
done < <(head /etc/passwd)
```

- It prints a list that contains usernames and user IDs separated by " -- "
- It prints something for all lines in `/etc/passwd`
- It prints something for the first line in `/etc/passwd`
- It prints something for the top 10 lines in `/etc/passwd`
- It generates a syntax error

### C++ compilation
Problem solving (20 pts)

Which statements will be true after the following code is executed?

```bash
#!/bin/bash

export CC=gcc-10
export CXX=g++-10

cd src
./configure
make && make check
sudo make install
```

- This script defines and exports two variables
- This script can be useful for compiling and installing a C++ library
- The `make check` command will be executed unconditionally
- This script uses absolute file references

### Create service
Language knowledge (20 pts)

Select all the correct statements regarding the following code. 

```bash
#!/bin/bash

function create-service() {
    service=$1
    cat <<EOT >> /tmp/${service}.service
[Unit]
Description=Example systemd service.

[Service]
Type=simple
User=root
ExecStart=/bin/bash /home/user/
RemainAfterExit=yes

[Install]
WantedBy=multi-user.target
EOT
}

create-service test
```

- It creates the file `/tmp/test.service`
- It creates the file `/tmp/service.service`
- It uses a "here" string
- It uses output redirection
- It only works as intended if the file exists before the script is executed

### Logical operator and variable scope in function
Language knowledge (20 pts)

Select the correct statement regarding the following code. 

```bash
#!/bin/bash

a=Linux

function a_date() {
	local a=$(date)
	[[ "$1" ]] && echo $a
}

a_date
echo $a
```

- It prints the current date and time
- It prints the text `Linux`
- It prints the current date and time in the first line and the text `Linux` in the second line
- It does not print anything

### NVME drives
Language knowledge (20 pts)

Select all the correct statements regarding the following code. 

```bash
#!/bin/bash

i=0
for d in nvme{0..24}n1
do
    [ -b /dev/${d} ] && mkdir /tmp/dir$i
    ((i++))
done
```

- It checks the existence of 25 NVME drives
- It creates directories for existing NVME drives
- It creates directories for NVME drives that are not available
- It uses the logical _and_ operator
- It uses the logical _or_ operator

### Path handling - array
Language knowledge (20 pts)

What would be the output of running the following command?

```bash
#!/bin/bash

filepath="/usr/local/lib/python3.7/dist-packages/google_auth_httplib2.py"

dname=$(dirname "$filepath")
dname=(${dname//\// })

echo ${dname[-2]}
```

- A syntax error
- `lib`
- `python3.7`
- `dist-packages`
- `local`
- `usr`

### basename
Language knowledge (20 pts)

Which commands can be used instead of `XXX` to get the filename from the `filepath` variable?

```bash
#!/bin/bash

filepath="/usr/local/lib/python3.7/dist-packages/google_auth_httplib2.py"

XXX

echo $filename
```

_Select all correct answers._

```text
filename=$(basename "$filepath")
```    
```text
filename=`basename "$filepath"`
``` 
```text
filename=${basename "$filepath"}
``` 
```text
filename='basename $filepath'
```

### IP or Port
Language knowledge (20 pts)

Select the correct statement regarding the following code. 

```bash
#!/bin/bash

port=
ipv4=

setup() {
    read port
    read ipv4
}

setup <<EOT
192.168.0.1
4567
EOT

echo $port
```

- It does not print anything
- It generates a syntax error
- It prints `192.168.0.1`
- It prints `4567`
- It prints:  
    `192.168.0.1`  
    `4567`

### Source and functions
Problem solving (20 pts)

What could you write instead of `XXX` to be able to use functions and variables that have been defined in the `common.sh` file? 

```bash
#!/bin/bash

XXX

for i in ${hosts[*]}; do
    # ...
done
```

_Select all the correct answers._
 ```bash
. common.sh
``` 
```text
source common.sh
```
```bash
import common.sh
``` 
```php
include common.sh
```

### Directory syncronization
Language knowledge (20 pts)

Select all the correct statements regarding the following code. 

```bash
#!/bin/bash

srcdir="/var/www/src"
destdir="$(basename $srcdir)/dst"

if [ -d "$srcdir" -a -d "$destdir" -a -w "$destdir" ]; then

    if [ $(diff -qr "$srcdir" "$destdir" | wc -l) -eq 0 ]; then
        echo "Two dirs are the same"
    else
        echo "Two dirs are different: updating"
        rsync --delete -a --inplace "$srcdir/" "$destdir"
    fi

else
    echo "Error accessing directories: $srcdir or $destdir"
fi
```

- It operates on two directories: `/var/www/src` and `/var/www/dst`
- It modifies the content of `destdir` only if it is writable
- It modifies the content of `srcdir` only if it is writable
- It modifies the content of both `srcdir` and `destdir`
- It operates on two directories: `/var/www/src` and `/var/www/src/dst`
- It operates on two directories: `/var/www/src` and `/var/dst`

### Mount + filtering
Language knowledge (20 pts)

What does the following script do?

```bash
#!/bin/bash

input_file="hdd_serial"

(cat << EOT
PATH	SERIAL
/dev/sdb	50026B724B037468
/dev/sdc	50026B724B037469
/dev/sdd	50026B724B037470
EOT
) > "$input_file"

while read -r line; do
    device=$(echo $line|cut -d' ' -f1)
    serial=$(echo $line|cut -d' ' -f2)
    [[ "$line" =~ ^/dev ]] &&  sudo mount $device /mnt/$serial
done < "$input_file"
```

- It creates or updates a file whose name is `hdd_serial`
- It will create an error if the file `hdd_serial` already exists
- It tries to mount 2 disks
- It tries to mount 3 disks
- It will create an error if the file `hdd_serial` does not exist

### Google ping and here string
Language knowledge (20 pts)

Select the correct statement(s) regarding the following code. 

```bash
#!/bin/bash

in='PING google.com (142.250.180.238) 56(84) bytes of data.
64 bytes from bud02s34-in-f14.1e100.net (142.250.180.238): icmp_seq=1 ttl=116 time=22.2 ms
64 bytes from bud02s34-in-f14.1e100.net (142.250.180.238): icmp_seq=2 ttl=116 time=17.6 ms
64 bytes from bud02s34-in-f14.1e100.net (142.250.180.238): icmp_seq=3 ttl=116 time=15.3 ms
64 bytes from bud02s34-in-f14.1e100.net (142.250.180.238): icmp_seq=4 ttl=116 time=14.0 ms'

while read s
do
	echo "**$s**"
done <<< "$in"
```

- It uses a "here" document
- It uses a "here" string
- It uses input redirection
- It uses command substitution

### Echo with variables and quotes 1
Language knowledge (20 pts)

What would be the output of running the following command?

```bash
#!/bin/bash

unset os
unset Linux

Linux=Debian
os=Linux
echo "$Linux GNU/$os"
```

- `$Linux GNU/$os`
- `Debian GNU/Linux`
- `Linux GNU/Debian`
- `Linux GNU/os`


