1. Put files with *txt* extension to *files.txt* (-mindepth 2 : include  subdirectories)
```bash
find ~/projects/human/ -mindepth 2  -name  *txt >> files.txt
```
2 - 5 _

6. Download *chr20.fa* and find all lines with sequence (-i : ignore a register)
```bash
wget https://github.com/rabix/rabix/raw/master/rabix/tests/test-files/chr20.fa
grep -i "ATGCATGCATGC" chr20.fa
```

7. Number of line with sequence
```bash
grep -i  -n  "ATGCCAGGCATTC" chr20.fa
```
**ANS : 1929**
8. Delete line contains *>chr20* (-v: select non-matching lines, -w:  lines which contain  matches  that  form  whole  words). *chr20_1.txt* is a file without *>chr20*

```bash 
grep -vwE ">chr20" chr20.fa >chr20_1.fa
```
9. Add to archive (-h: human-readable format , -s: size of archive)
```bash
gzip chr20_1.fa
ls -hs chr20.fa.gz
```
**ANS: 19M**

10. Provide access  rights to all
```bash
chmod 777 chr20.fa.gz
```
