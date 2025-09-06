Практическое задание 1
----------------------------

cat /etc/passwd | cut -d: -f1 | sort

Практическое задание 2
----------------------------

awk '{print $2, $3}' /etc/protocols | sort -k1, -n -r | head -n 5

Практическое задание 3
----------------------------

touch banner

nano banner

#!/bin/bash

TEXT="$*"

LEN=${#TEXT}

LINE=$(printf '%*s' $((LEN + 2)) | tr ' ' '-')

echo "+$LINE+"

echo "| $TEXT |"

echo "+$LINE+"

./banner "Hello from RTU MIREA"

Практическое задание 4
----------------------------

