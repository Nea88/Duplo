Duplo

Клиентский скрипт для создания и деплоя проектов использузя докку.

Установка:
sudo cp duplo /bin 
или 
sh duplo-install

Использование:

duplo config:set <type> <url|name>      type - <dev|testing|user|prod>
устанавливает параметры: url dev/pro/test серверва и имя юзера, от имени которго билдяться дев сборки
Пример:
$duplo config:set user ivan
$duplo config:set bla.com ivan

duplo config:get <type>                 type - <dev|testing|user|prod>
возращает текущее значение параметра

duplo create <appType> <appName>        creates projects appType-<wp>
создает типовой проект
Пример:
$duplo create wp bla

duplo deploy:dev                        deploys app in current folder type to development server
отправляет сборку на дев сервер
duplo deploy:testing                    deploys app in current folder type to testing server
отправляет сборку на тестинг сервер
duplo deploy:prod <prod domains>        deploys app in current folder type to production server
отправляет сборку в продакшн, через пробел можно указать урл по которым должен быть доступен проект (либо можно использовать файл DOMAINSв сборке wp)



