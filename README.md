# postgres

This is just a simple repository to create a local container that has postgres and pgadmin in it, to local development for web applications that require a db layer.

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
