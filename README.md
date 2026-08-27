# diff
## Бинарные разницы между версиями моих разработок

Что это такое и для чего это нужно?

Я разработал платное ПО. Клиент его скачал, оплатив за мою работу. Затем я выпускаю новую версию своего ПО. Но я не хочу, чтобы клиент заново оплачивал новую версию. Как мне передать новую версию клиенту, не имея с ним никаких контактов? В этом поможет _БИНАРНЫЙ ПАТЧЕР_.

Суть его в следующем: я создаю бинарную разницу между конкретными версиями своего ПО. Получается небольшой файлик - патч для бинарников. Его я могу свободно выложить в открытый доступ. Клиент, имея у себя оригинальную версию моего ПО и данный патч, сможет легко создать у себя новую версию моего ПО, просто пропатчив предыдущую версию. Кто не имеет предыдущей версии, для него патч-файл представляет из себя просто бинарный мусор.

Программа-патчер: *DiffSV.exe*

Это сборка на .NET Framework, которая будет работать на любой ОС, где есть платформа от MS.

```
DiffSV (ver. 1.0 for infostart.ru)
DiffSV utility is a data comparison tool that calculates and writes to the file the differences between two files.
Also this utility can get the updated file from primary file and his difference file.

DiffSV.exe [-c -o [path]filename -n [path]filename -d [path]filename] [-a -o [path]filename -d [path]filename -n [path]filename] [-l] [-s] [-h]

-c      Create difference file between two files (available in full version only)
-a      Apply a patch for the primary file
-o      Old file
-n      New file
-d      Difference file
-l      License
-s      Silent mode
-h      Help information

Example of creating a difference file (for win):
DiffSV.exe -c -o oldfile.bin -n newfile.bin -d result.diff

Example of obtaining a patched file (for nix):
mono DiffSV.exe -a -o /home/userus/f0.bin -d /home/userus/diff.bin -n patched.bin

Powered by bsdiff (see license with key -l)
```

P.S. Ключ -c в этой версии работать не будет. Т.е. этот DiffSV.exe предназначен только для пропатчивания файлов, но НЕ для создания патчей.
