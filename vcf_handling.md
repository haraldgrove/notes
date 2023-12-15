# BCFtools

Filter on one tag in the INFO column, include all entries with length -50 <= x <= 50:
```
bcftools filter -i'INFO/SVLEN<51 && INFO/SVLEN>-51' file.vcf > file.sv50.vcf
```

Create a filter based on the length of a value in a column, exclude all entries with REF and the first ALT allele is a single base
```
bcftools filter -e'(STRLEN(REF)==1) && (STRLEN(ALT[0])==1)' merge_output.vcf.gz > merge_output.snv.vcf
```
