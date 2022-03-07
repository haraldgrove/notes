# linux

## FIND
```
find . -name "outTable*" -exec gzip {} \;
```

find will execute grep and will substitute {} with the filename(s) found. The difference between ; and + is that with ; a single grep command for each file is executed whereas with + as many files as possible are given as parameters to grep at once.

## AWK

Set field separator to TAB and print column 40
```bash
$ awk 'BEGIN { FS = "\t" } ; {print $40}'
```

Output rows where field 40 contains “1”
```bash
$ awk 'BEGIN { FS = "\t" } ; $40 ~ /1/ {print $40}'
```

Output column 40 in row 2 and any row with “1” in column 40 
```awk
$ awk 'BEGIN { FS = "\t" } ; NR == 2 {print $40} ; $40 ~ /1/ {print $40}'
```

## Command line

Add stderr to stdout and direct to a file
```bash
comman.sh > output.txt 2>&1
```
