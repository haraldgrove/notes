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

Changing the value of column 2, print whole line
```bash
$ awk '$2=$2-1' FS='\t' OFS='\t'
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

## Grep

Regex search for a pattern with known start and stop. The '-P' is for running grep with Perl-based regex. '?' indicates a non-greedy search, i.e. stop at first occurance of stop criteria.
```
grep -P -o "SYMBOL=.+?;" 
grep -P -o "SYMBOL=.+?(?=;)"
```
Example: search for entries starting with 'SYMBOL=' and stops at the first ';'. First line includes the ';', the second omit it.

## Sort

```bash
sort chrom.bed                   # chr1,chr10-19,chr2,chr20-22,chr3-9,chrM,chrX,chrY
sort -V -k1,1 -k2,2 chrom.bed    # chr1-22,chrM,chrX,chrY
sort -R chrom.bed                # Random order
sort -n 
```
## Prepare environment for first time use

Install GCC (C compiler)
```bash
sudo apt update
sudo apt install build-essential
sudo apt install zlib1g-dev
sudo apt install libncurses5-dev
sudo apt install libbz2-dev
sudo apt install liblzma-dev
sudo apt install libcurl4-openssl-dev
```

## Change prompt

Add this to ~/.bashrc to make it permanent

Two line prompt, first line shows current folder, second line shows user and host. With fancy colors (the XXm part).
```bash
export PS1="\[\033[34m\][\w]\[\033[0m\]\n\[\033[0;31m\]\u\[\033[0;33m\]@\[\033[36m\]\h\[\033[35m\]-> \[\033[0m\]"
```
