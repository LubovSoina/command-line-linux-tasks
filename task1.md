1. Create system of subdyectories and files

```bash
mkdir ~/projects
mkdir ~/projects/{human,mouse,fly}
mkdir ~/projects/human/{hg19,hg38}
touch ~/projects/mouse/{genes,proteins}.txt
```
2. Set directory to find file *genes.txt* and add 5 lines in text redactor *nano*

```bash
cd ~/projects/mouse/
nano genes.txt
```
**echo**

```bash
touch genes.txt
echo -e "ATACTACTTCCAAGG \nTGGGCTACTTCCAAGG \nATGATCTACTATATATA \nGGTATGCCT \nTTTTTTAGA">genes.txt
```
3. Copy file to another folder and add 5 more lines

```bash
cp genes.txt ~/projects/human/hg38
cd ~/projects/human/hg38
nano genes.txt
```
**echo**
```bash
echo -e "ATACTACTTCCG \nTGGGCTAC \nATGATTTTTATA \nAAAAACCT \nTTTGAGAGAAGA">>genes.txt
```
4. Output on dysplay (R means: list subdirectories recursively)
```bash
ls -R ~/projects
```
5. Sort lines in file and output on dysplay
```bash
sort genes.txt| cat
```
6. Sort lines and remove to another file
```bash
sort genes.txt >> ~/projects/human/hg19/genes.txt
```
7. Rename file
```bash
cd ~/projects/human/hg19/
~/projects/human/hg19$ mv genes.txt genes.tab
```
8. Put first 3 rows to another file (sed -n `1,3` : take 3 first rows)
```bash
cat genes.tab|sort|sed -n '1,3p' >>genes1.txt
```
9. Output number of lines *genes.tab*
```bash
wc -l genes.tab
```





