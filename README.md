# PHP8環境

## 構成
* docker compose
* app - php
* web - nginx
* db  - mysql

### web
* port: 8888 -> 80
* directory: /var/www/html
* conf: nginx.conf
* login: docker compose exec web sh

### app
* port: 9999
* directory: /var/www/html
* conf: php.ini zz-docker.conf
* login: docker compose exec app bash

### db
* port: 33060
* directory: /var/lib/mysql
* conf: my.cnf
* login: docker compose exec db bash
