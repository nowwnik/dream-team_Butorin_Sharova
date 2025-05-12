## Конфигурация

Для настройки БД из [docker-compose.yml](./docker-compose.yml) в контейнеры передаются файлы конфигурации:

master_server:
* [postgresql.conf](./master_server/postgresql.conf)
* [pg_hba.conf](./master_server/pg_hba.conf)

standby_server:
* [postgresql.conf](./standby_server/postgresql.conf)
* [pg_hba.conf](./standby_server/pg_hba.conf)
* [init.sh](./standby_server/init.sh)


## Демонстрация

Поднимаем контейнеры
```shell
cd 2.postgres_cluster
docker compose up
```
Подключаемся к `master_server`
```shell
psql -h localhost -p 5433 -U postgres
```

Подключаемся к `standby_server`
```shell
psql -h localhost -p 5434 -U postgres
```

Убиваем `master_server`
```
docker stop master_server
```