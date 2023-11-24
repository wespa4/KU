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
most_common_word=$(find $directory_path -type f -exec cat {} + | tr -sc '[:upper:]' '\n' | tr '[:upper:]' '[:lower:]' | sort | uniq -c | sort -nr | awk '{print $2}' | head -1)

echo "Most common word in files in $directory_path is: $most_common_word"
```
### Задание 2
С помощью команд эмулятора git получить состояние проекта, как на картинке
<img width="624" alt="Снимок экрана 2023-11-24 в 18 32 30" src="https://github.com/wespa4/KU/assets/145107412/503be5a2-996b-48ae-8c3e-dba628bf33cf">
### Решение
```sh
//список команд:
git branch unwomanly
git commit
git checkout unwomanly
git commit
git checkout master
git commit
git branch drop-down
git commit
git commit
git branch dipped
git checkout drop-down
git commit
git checkout unwomanly
git rebase drop-down
```
