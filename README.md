# WEBIM SETUP

make sure you have webim in the same directory as this repo or if not you can change it in .env file

```shell
git clone https://github.com/bendavies99/docker-compose-lamp.git
cd docker-compose-lamp/
git fetch --all
git checkout 5.6.x
docker-compose up -d
```

docker-compose up -d to start the containers

docker-composer stop to stop the containers

docker-composer kill to kill the containers

make sure in libs/config.php you change the settings to

mariadb for the host

root for the username

tiger for the password

```php
$mysqlhost = 'mariadb';
$mysqldb = 'webim';
$mysqllogin = 'root';
$mysqlpass = 'tiger';
$mysqlprefix = '';
```

then you will need to setup up the database goto localhost:8100 for PMA and then create a database called webim and then import the SQL file found at install/webim.sql and turn off enablessl and forcessl in chatconfig

### finally goto localhost:80/webim

## Happy developing!

### Configuration Variables

There are following configuration variables available and you can customize them by overwritting in your own `.env` file.

_**DOCUMENT_ROOT**_

It is a document root for Apache server. The default value for this is `./www`. All your sites will go here and will be synced automatically.

_**MYSQL_DATA_DIR**_

This is MySQL data directory. The default value for this is `./data/mysql`. All your MySQL data files will be stored here.

_**VHOSTS_DIR**_

This is for virtual hosts. The default value for this is `./config/vhosts`. You can place your virtual hosts conf files here.

> Make sure you add an entry to your system's `hosts` file for each virtual host.

_**APACHE_LOG_DIR**_

This will be used to store Apache logs. The default value for this is `./logs/apache2`.

_**MYSQL_LOG_DIR**_

This will be used to store Apache logs. The default value for this is `./logs/mysql`.
