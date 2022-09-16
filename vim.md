# Duplicate the line
```
:%s/.*/& &/
```

.* means everything, starting from the first match, which is any character; so that gets the whole line.

& copies everything that was matched, so here that's the whole line. Twice.
