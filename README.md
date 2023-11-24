# KU
## Контрольная работа
### Задание 1
Написать программу, которая выводит на экран самое часто встречающееся слово (последовательность непробельных символов) среди файлов в каталоге, заданном аргументом командной строки
### Решение
```sh
#!/bin/bash

if [ -z "$1" ]; then
    echo "Usage: $0 <directory_path>"
    exit 1
fi
directory_path=$1
most_common_word=$(find $directory_path -type f -exec cat {} + | tr -sc 'A-Za-z' '\n' | tr 'A-Z' 'a-z' | sort | uniq -c | sort -nr | awk '{print $2}' | head -1)

echo "Most common word in files in $directory_path is: $most_common_word"
```
### Задание 2
### Решение
