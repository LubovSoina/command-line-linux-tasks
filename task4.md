1. Приветсвующий скрипт
```bash
#! /bin/bash
echo "Hello,world!"
```
2. Ввод строки пользователем и вывод ее на экран
```bash
#! /bin/bash
echo "Ведите строку символов"
read m
echo "Вы ввели: $m"
```
 3. Вывод на экран размер файлов с расширением **.txt*
 ```bash
 #! /bin/bash
echo "$(ls -l --b=K  *.txt|cut -d " " -f5)"
```
4. Вывод имен всех **.txt* без расширения
```bash
#! /bin/bash
echo "$(ls -l  *.txt|cut -d " " -f9| cut -d "." -f1)"
```
5. Вывод имени, размера, даты создания и количсетва строк файла-параметра
```bash
#! /bin/bash
echo "name $(ls -l  $1|cut -d " " -f9| cut -d "." -f1)"
echo "size $(ls -l --b=K  $1|cut -d " " -f5)"
echo  "time $(ls -l --b=K  $1|cut -d " " -f6-8)"
echo "num of strings $(wc -l $1| cut -d " " -f1)"
```
6. Вывод строки 100 раз
```bash
#! /bin/bash

read str
for ((i=1; i <= 100; i++))
do
echo $str
done
```
7. Вывести на экран строки из файла с *Line*
```bash
#!/bin/bash
input=$1
while IFS= read -r line
do
  echo "Line: $line"
done < "$input"
```
8. Сумма двух чисел
```bash
#! /bin/bash
let "c = $1+$2"
echo $c

```

9. Привествие, при строке *hello*
```bash
#! /bin/bash
read str
if [[ $str == "hello" ]]
then
 echo "hello"
else
 exit
fi
```
10. Результат скриптов 3 и 6 в один файл
```bash
#! /bin/bash
echo "$(ls -l --b=K  *.txt|cut -d " " -f5)" >> text.txt
read str
for ((i=1; i <= 100; i++))
do
 echo $str 
done >>text.txt
```


