1. Count number of lines in *chr20.fa* with sequence
```bash
grep -ic "ATGCATGCATGC" chr20.fa
```
**ANS: 16**


2. Count number of lines starts with sequence 
```bash
grep -E -ic  "^ATGC" chr20.fa
```
**ANS: 4003**


3. Count number of lines starts and ends with sequence 
```bash
grep -E -ic "^ATGC.*ATGC$" chr20.f
```
**ANS: 11**


4. Count "N" 
```bash
cat chr20.fa|grep -E "N"|wc -m
```
**ANS: 3590676**

5_6


7. Output 20 first sorted lines with seq (-m : dont search after a given occurrence)
```bash
cat chr20.fa|grep -im 20 "ATGCTCG"|sort
```

8. Count nucleotid sequence (??)
```bash
wc -m chr20.fa
```
9. Find line with max T repeatings 
```bash 
grep -E -in 'T' chr20.fa|sort -k1.9|tail
```
**ANS: 776435,91077**

10. Output sorted palindromes from 10 character
```bash
cat chr20.fa|grep -E -e '(.)(.)(.)(.)(.)\5\4\3\2\1'|sort > pol.txt
```
