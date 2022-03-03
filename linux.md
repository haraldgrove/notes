---
title: linux
created: '2022-03-03T03:53:35.602Z'
modified: '2022-03-03T03:54:18.573Z'
---

# linux

## FIND
```
find . -name "outTable*" -exec gzip {} \;
```

find will execute grep and will substitute {} with the filename(s) found. The difference between ; and + is that with ; a single grep command for each file is executed whereas with + as many files as possible are given as parameters to grep at once.

