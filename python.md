# Grep

Search for a word based on the characters in front and behind. Works with different alternatives for the ending parameter

```
import re
line = gene_id "ENSG00000270136"; gene_version "6"; transcript_id "ENST00000602384";
gene_name = re.search(r'transcript_id(.*?)[;|\t]',line).group(1)
print(gene_name)
```
ENST00000602384

Iterate over the given pattern
```
[m.start() for m in re.finditer('(?=tt)', 'ttt')]
```
