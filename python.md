# Grep
```
import re
line = gene_id "ENSG00000270136"; gene_version "6"; transcript_id "ENST00000602384";
gene_name = re.search(r'transcript_id(.*?);',line).group(1)
print(gene_name)
```
ENST00000602384
