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
    
    //--//
    #!/bin/bash

    TEXT="$*"
    LEN=${#TEXT}
    LINE=$(printf '%*s' $((LEN + 2)) | tr ' ' '-')

    echo "+$LINE+"
    echo "| $TEXT |"
    echo "+$LINE+"
    //--//
    
    chmod +x banner
    ./banner "Hello from RTU MIREA"

Практическое задание 4
----------------------------

touch getIdentifiers

nano getIdentifiers

//--//

FILE="$1"

grep '\b[a-zA-Z_][a-zA-Z0-9_]*\b' "$FILE" | sort -u | tr '\n' ' '

echo

//--//

chmod +x getIdentifiers

./getIdentifiers hello.c

Практическое задание 5
----------------------------

touch comSch

nano comSch

//--//

#!/bin/bash

FILE="$1"


if [[ "$FILE" != *.js && "$FILE" != *.py ]]; then

    exit 1
    
fi

if head -1 "$FILE" | grep -E '^[[:space:]]*(//|#)' > /dev/null; then

    echo "✅ Comment found on first line"
    
    exit 0
    
else

    echo "❌ No comment on first line"
    
    exit 1
    
fi

//--//




