# bash

## Loops

For loop
```bash
for i in {1..100}
do
 echo $i
done
```

While loop
```bash
i=1
while [[ $i -lt 100 ]] ; do
   echo "$i"
  (( i += 1 ))
done
```

Loop over lines in a file
```bash
SAMPLEFILE=file.txt
LINES=$(cat $SAMPLEFILE)
for line in $LINES
do
        echo $line
done
```

Loop over folders starting with “name”, and split the folder name
```bash
LINES=$(ls -d -1 name*)
for line in $LINES
do
    IFS='_' read -ra ADDR <<< "$line"
    SAMPLE="${ADDR[1]}"
    ID="${ADDR[2]}"
    echo $line
Done
```
```bash
SAMPLES=$1

echo ${SAMPLES}

LINES=$(cat $SAMPLES)

for line in $LINES
do
        IFS="," read -a arr <<< $line
        echo "My array: ${arr[@]}"
        echo "Number of elements in the array: ${#arr[@]}"
        for (( i=0; i<=${#arr[@]}; i++ )); do
                echo "${arr[$i]}"
        done
Done
```

## IF-ELIF-ELSE
```bash
if TEST-COMMAND1
then
  STATEMENTS1
elif TEST-COMMAND2
then
  STATEMENTS2
else
  STATEMENTS3
fi
```

```bash
#!/bin/bash

echo -n "Enter a number: "
read VAR

if [[ $VAR -gt 10 ]]
then
  echo "The variable is greater than 10."
elif [[ $VAR -eq 10 ]]
then
  echo "The variable is equal to 10."
else
  echo "The variable is less than 10."
fi
```

```
if [[ $VAR1 -ge $VAR2 ]] && [[ $VAR1 -ge $VAR3 ]]
```

### Test operators
To negate the test expression, use the logical NOT (!) operator.

* -n VAR - True if the length of VAR is greater than zero.
* -z VAR - True if the VAR is empty.
* STRING1 = STRING2 - True if STRING1 and STRING2 are equal.
* STRING1 != STRING2 - True if STRING1 and STRING2 are not equal.
* INTEGER1 -eq INTEGER2 - True if INTEGER1 and INTEGER2 are equal.
* INTEGER1 -gt INTEGER2 - True if INTEGER1 is greater than INTEGER2.
* INTEGER1 -lt INTEGER2 - True if INTEGER1 is less than INTEGER2.
* INTEGER1 -ge INTEGER2 - True if INTEGER1 is equal or greater than INTEGER2.
* INTEGER1 -le INTEGER2 - True if INTEGER1 is equal or less than INTEGER2.
* -h FILE - True if the FILE exists and is a symbolic link.
* -r FILE - True if the FILE exists and is readable.
* -w FILE - True if the FILE exists and is writable.
* -x FILE - True if the FILE exists and is executable.
* -d FILE - True if the FILE exists and is a directory.
* -e FILE - True if the FILE exists and is a file, regardless of type (node, directory, socket, etc.).
* -f FILE - True if the FILE exists and is a regular file (not a directory or device).

## Concatenate STRING variables
```bash
VAR=""
for ELEMENT in 'Hydrogen' 'Helium' 'Lithium' 'Beryllium'; do
  VAR+="${ELEMENT} "
done

echo "$VAR"
```

## Slice STRING

Split a string in 2 parts: the first N-4 characters and the last 4 characters.
```bash
string=$1
let a=${#string}-4
first=${string:0:$a}
second=${string:(-4)}
```
