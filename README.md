# My notes about using MySQL with docker

This is just a collection of scripts, tutorials, links, articles, commands or any other resource about using docker for [MySQL](https://www.mysql.com/) or [MariaDB](https://mariadb.com/). Because I have to search for it again adn again every time I need it.

## MySQL8

> WARNING: We are not using a persisted volume. If you remove the volume used by the container you lose the database data.

Run the docker container and connect using the console client:

```s
./bin/start_mysql.sh
./bin/mysql_client.sh
```

## Commands using your client

How to run commands using the console client.

Run the client:

```s
mysql -h127.0.0.1 -uroot -pdb-root-password
```

Run a SQL sentence:

```s
mysql -h127.0.0.1 -uroot -pdb-root-password torrust_v1 < ./your.sql
```

## Commands using the dockerized client

Run a SQL sentence:

```s
docker exec -i torrust-index-backend-mysql mysql torrust_v1 -uroot -pdb-root-password < ./your.sql
```

## Other commands

Backup DB:

```s
mysqldump -h127.0.0.1 torrust_v1 -uroot -pdb-root-password > ./schema_dump.sql
```
