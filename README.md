#Duplo

##Client-side script for creates and deploying projects in dokku.
*now working only with wordpress && docpad

Install:
```
$cd Duplo
$sh duplo-install
```

##Using:

`duplo config:set <type> <url|name>      type - <dev|testing|prod|user>`
sets dev/production/testing url and user name

Example:

```
$duplo config:set user ivan
$duplo config:set dev bla.com
```


`duplo config:get <type>                 type - <dev|testing|prod|user>` shows param

`duplo create <appType> <appName>        creates projects appType-<wp|docpad>` creates project by type

Example:
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

`duplo deploy:dev` deploy in dev (using url app-name-user_name.dev_url)

`duplo deploy:testing` deploy in testing (using url app-name.testing_url)

`duplo deploy:prod <prod domains>` deploy in production with custom urls (or you can add DOMAINS file in your root project)


