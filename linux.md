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

Output the first row and any subsequent rows where field 40 contains "1"
```bash
$ awk 'BEGIN {FS = "\t"} ; NR==1 ; $40 ~ /1/ {print $0}'
```

Output column 40 in row 2 and any row with “1” in column 40 
```bash
$ awk 'BEGIN { FS = "\t" } ; NR == 2 {print $40} ; $40 ~ /1/ {print $40}'
```

## Command line

Add stderr to stdout and direct to a file
```bash
comman.sh > output.txt 2>&1
```

## Replacing text in files

Replace a word in one or more files, can also read from standard input.
```bash
sed 's/word1/word2/g' input.file
```

Replace in-place (-i), add more replacement commands (-e)
```bash
sed -i 's/word1/word2/g' input.file
sed -i -e 's/word1/word2/g' -e 's/xx/yy/g' input.file
```

Other characters can also be used as separator
```bash
## Use + separator instead of / ##
sed -i 's+regex+new-text+g' file.txt
```

Replace only when certain conditions are met (e.g. FOO is found on the line)
```bash
sed -i -e '/FOO/s/love/sick/' input.txt
```

Add search parameters: find all occurances (g), ignore case (I)
```bash
sed -i 's/word1/word2/gI' input
```
