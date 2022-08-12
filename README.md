# postgres

This is just a simple repository to create a local container that has postgres and pgadmin in it, to allow local development for web applications that require a db layer.

## Run postgres and pgadmin

1. Requires Docker on machine
2. git clone repo
3. Run `docker compose up` to download and run the postgres and pgadmin images listed in the `docker-compose.yaml`
4. Link to locally running pgadmin: <http://localhost:5050>
5. Login to pgadmin (can change this in `docker-compose.yaml`)
   1. `username: user@email.com`
   2. `password: password`
6. Use the following connection string to connect to postgres from your local web app:
   1. `DB_CONNECTION_STRING="postgresql://postgres:password@localhost:5432/postgres"`

### Backup database

<https://inedo.com/support/kb/1145/accessing-a-postgresql-database-in-a-docker-container>

1. Run `docker exec -u postgres db pg_dump -Cc | xz > backup-$(date -u +%Y-%m-%d).sql.xz`
2. Postgres backup will be in the directory you ran the command from

### Restore database from backup

1. Run `xz -dc <backup-file-name>.sql.xz | docker exec -i db psql -U postgres`
