# Микротик Эксплойт Сканирование и экспорт логина и пароля RouterOS позволяют сканировать подсеть IPv4 в цикле с портом 8291 или заданным. Используется протокол WinBox.
все результаты будут выводится на экран, а так же записаны в файл rezult.txt

## Установка


##### Установка в Windows PowerShell
```
install Git https://git-scm.com/download/win
install Python https://www.python.org/downloads/
install PowerShell https://github.com/PowerShell/PowerShell/releases/
$ pip install -r requirements.txt

```

##### Clone the repository
```
$ git clone https://github.com/nebbbes/mikrotik
$ cd mikrotik
```
## Команды
сканировать один IP: *В корневом каталоге скрипта*
```
$ python loop.py 192.168.1.10
```
сканирование с другим портом
```
$ python loop.py 192.168.1.10 -p 8282
```
Диапазон сканирования IP
```
$ python loop.py 192.168.1.0/24
````
сканировать список IP из файла

```
$ python loop.py -f list.txt
```
## Не работает на некоторых версиях: все версии до 6.45.9 работает, выше нет.

## Защита маршрутизатора **Обновите RouterOS и ограничьте вход в Winbox**
```
IP-фильтр брандмауэра добавить цепочку chain=input in-interface=wan protocol=tcp dst-port=8291 action=drop
```

