1. Используйте команды операционной системы Linux и создайте две новых директории – «Игрушки для школьников» и «Игрушки для дошколят»
```powershell
nevol78@ubuntu11:~$ mkdir Игрушки_для_дошколят
nevol78@ubuntu11:~$ mkdir Игрушки_для_Школьников
```
2. Создайте в директории «Игрушки для школьников» текстовые файлы - «Роботы», «Конструктор», «Настольные игры»
```powershell
nevol78@ubuntu11:~$ cd Игрушки_для_Школьников
nevol78@ubuntu11:~/Игрушки_для_Школьников$ > Роботы
nevol78@ubuntu11:~/Игрушки_для_Школьников$ > Конструктор
nevol78@ubuntu11:~/Игрушки_для_Школьников$ > Настольные_Игры
```
3. Создайте в директории «Игрушки для дошколят» текстовые файлы «Мягкие игрушки», «Куклы», «Машинки»
```powershell
nevol78@ubuntu11:~/Игрушки_для_Школьников$ cd ..
nevol78@ubuntu11:~$ cd Игрушки_для_дошколят
nevol78@ubuntu11:~/Игрушки_для_дошколят$ > Мягкие_Игрушки
nevol78@ubuntu11:~/Игрушки_для_дошколят$ > Куклы
nevol78@ubuntu11:~/Игрушки_для_дошколят$ > Машинки
```
4. Объединить 2 директории в одну «Имя Игрушки»
```powershell
Здесь я наперед выполняю задачу под номером 7
nevol78@ubuntu11:~/Игрушки_для_дошколят$ cd
nevol78@ubuntu11:~$ sudo snap install tree
[sudo] password for vm:
tree 1.8.0+pkg-3fd6 from 林博仁(Buo-ren, Lin) (brlin) installed
nevol78@ubuntu11:~$ tree
nevol78@ubuntu11:~$ mkdir Имя_Игрушки
nevol78@ubuntu11:~$ mv Игрушки_для_Школьников/ Игрушки_для_дошколят/ Имя_Игрушки/
nevol78@ubuntu11:~$ cd Имя_Игрушки
nevol78@ubuntu11:~/Имя_Игрушки$ tree
```
5. Переименовать директорию «Имя Игрушки» в «Игрушки»
```powershell
nevol78@ubuntu11:~/Имя_Игрушки$ cd
nevol78@ubuntu11:~$ mv Имя_Игрушки/ Игрушки
nevol78@ubuntu11:~$ ls
```
6. Просмотреть содержимое каталога «Игрушки».
```powershell
nevol78@ubuntu11:~$ cd Игрушки
nevol78@ubuntu11:~/Игрушки$ tree -g
```
7. Установить и удалить snap-пакет. (Любой, какой хотите)
   Установка пакета была в пункте 4
```powershell
nevol78@ubuntu11:~/Игрушки$ sudo snap remove tree
tree removed
```
8. Добавить произвольную задачу для выполнения каждые 3 минуты
   (Например, запись в текстовый файл чего-то или копирование из каталога А в каталог Б).
```powershell
nevol78@ubuntu11:~/Игрушки$ sudo vi /usr/local/bin/script.sh
    #!/bin/bash
    echo $(date) >> /var/log/testcron.log
    :w!
    :q
nevol78@ubuntu11:~/Игрушки$ sudo chmod ugo+x /usr/local/bin/script.sh
nevol78@ubuntu11:~/Игрушки$ sudo crontab -e
    0/3 * * * * /usr/local/bin/script.sh
crontab: installing new crontab
```
