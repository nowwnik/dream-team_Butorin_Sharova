# dream-team_Butorin_Sharova

Разворачивать на двух машинах было сложно, и не получилось, поэтому вот, контейнер

1. Склонировать репозиторий
2. Запустить контейнер
```cd 2.postgres_cluster```
```docker compose up ```
3. Подключение master
```psql -h localhost -p 5433 -U postgres```
4. Подключение standby
```psql -h localhost -p 5434 -U postgres```
