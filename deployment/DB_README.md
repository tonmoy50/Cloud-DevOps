### Project Structure

```
postgres
|__ database.env
|__ docker-compose.yml
|__ pgdata/
```
`docker-compose.yml` file should have following code:

```
version: "3.8"
services:
  db:
    image: "postgres:latest"
    restart: always
    env_file:
      - database.env
    ports:
      - "5432:5432"
    volumes:
      - ./pgdata:/var/lib/postgresql/data

  adminer:
    image: adminer
    restart: always
    ports:
      - 8080:8080

```
`database.env` file should have following values set:

```
POSTGRES_USER=USERNAME
POSTGRES_PASSWORD=PASSWORD
POSTGRES_DB=DBNAME
```

Note: There should not be any space between environment variable name and value

##### To start the postgres container in detach mode, run the command:

```
docker-compose up --build -d
```

### Resources
1. [Postgres up and running in less than 3 minutes with docker-compose](https://dev.to/raphaelmansuy/postgres-up-and-running-in-less-than-3-minutes-with-docker-compose-1odd)
