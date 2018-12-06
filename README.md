# linux_commands
# Полезные команды Linux

### объем свободного пространства
```sh
df
```

### объем свободной памяти
```sh
free
```

### перейти в предыдущую рабочую папку
```sh
cd -
```

### перейти в рабочую папку пользователя user1
```sh
cd ~user1
```

### вывести тип файла
```sh
file <name>
```

### вывести содержимое файла
```sh
less <name>
```

### получение типа команды (проверить, если ли такая команда)
```sh
type <name>
```

### где находится выполняемый файл
```sh
which <имя>
```

### вывод списка подходящих команд
```sh
apropos <keyword>
```

### создать псевдоним команды
```sh
alias mytest='<commands separated by ;>'
```

### создать пустой файл
```sh
> <имя файла>
```


### перенаправление вывода ошибок
```sh
... 2> error.txt
```

### перенаправление всех сообщений (в том числе и ошибок)
```sh
... > log.txt 2>&1
```
или
```sh
... &> log.txt
```


### вывод журнала сообщений в режиме реального времени
```sh
tail -f /var/log/syslog
```

### пример использования подстановки {} - создание каталогов с именами 01 - 99.
```sh
mkdir 0{1..9} {10..99}
```

### вывод имен и значений переменных окружения
```sh
printenv | less
```

### вывести историю команд
```sh
history 
```

### поиск в истории команд
```sh
CTRL-R
```

### запустить командную оболочку от имени суперпользовалеля
```sh
su -
```

### изменить владельца файла
```sh
chown ...
```

### какие процессы работают
```sh
ps x
ps aux
```

### вывод процессов в реальном времени
```sh
top
```

### запустить процесс в фоновом режиме
```sh
xlogo &
```

### список процессов
```sh
jobs
```

### вывод сведений о памяти
```sh
vmstat
```

### активировать изменения без перезапуска терминала
```sh
source .bashrc
```

### информация о файле
```sh
stat <имя файла>
```

### удалить все файлы *.bak в папке пользователя
```sh
find ~ -type f -name '*.bak' -delete
```

### передать каталог (Files) с удаленной машины (comp1) на локальную с использованием tar
```sh
ssh comp1 'tar cf - Files' | tar xf -
```

### бэкап каталогов /etc /home /usr/local на внешний диск (/media/ssd200/archive) с использованием синхронизации:
```sh
sudo rsync -av --delete /etc /home /usr/local /media/ssd200/archive
```
### или создать псевдоним команды:
```sh
alias makebkp='sudo rsync -av --delete /etc /home /usr/local /media/ssd200/archive'
```

### найти самые объемные каталоги в папке пользователя
```sh
du -s ~ | sort -nr | head
```

### если сбивается время в Windows после запуска Ubuntu
```sh
sudo timedatectl set-local-rtc 1 --adjust-system-clock
```

### для переключения раскладки клавиатуры по Shift+Alt - установить gnome-tweaks:
```sh
sudo apt-get install gnome-tweak-tool
```
