#Duplo

##Клиентский скрипт для создания и деплоя проектов используя dokku.

Установка:
windows:

```
$git clone https://github.com/Nea88/Duplo.git
$cd duplo
$cp duplo /bin
```

linix:

```
$git clone https://github.com/Nea88/Duplo.git
$cd duplo
$sh duplo-install
```

##Использование:

`duplo config:set <type> <url|name>      type - <dev|testing|prod|user>`
устанавливает параметры: url dev/production/testing серверов соответствено, а также имя юзера, от имени которго собираются дев сборки
Ключ --global устанавливает параметры глобально для всех проектов. Параметры для проектаимеют больштй приоритет. 
Параметр user - глобальный по умолчанию.

Пример:

```
$duplo config:set user ivan
$duplo config:set --global dev bla.com
```


`duplo config:get <type>                 type - <dev|testing|prod|user>` выводит текущее значение параметра

`duplo create <appType> <appName>        creates projects appType-<wp|docpad|other>` создает типовой проект

Пример:
```
$ duplo create wp bla
----> Start creating wp app
Cloning into bla...
remote: Reusing existing pack: 1344, done.
remote: Counting objects: 9, done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 1353 (delta 4), reused 0 (delta 0)
Receiving objects: 100% (1353/1353), 4.90 MiB | 299 KiB/s, done.
Resolving deltas: 100% (304/304), done.
[master a5cabed] Added project name and persistent storage files
 2 files changed, 2 insertions(+), 0 deletions(-)
 create mode 100644 PERSISTENT_STORAGE
 create mode 100644 PROJECT_NAME
----> bla created
```

`duplo deploy:dev` отправляет проект на дев сервер
`duplo deploy:testing` отправляет сборку на тестинг сервер
`duplo deploy:prod <prod domains>` отправляет сборку в продакшн, параметром можно указать урл по которым должен быть доступен проект (либо можно использовать файл DOMAINS в корне проект)



