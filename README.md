# todoapp-flask [![Circle CI](https://circleci.com/gh/stefanteixeira/todoapp-flask.svg?style=shield)](https://circleci.com/gh/stefanteixeira/todoapp-flask)

To init a PostgreSQL database container for the project:

```docker run -d --name postgresql -e 'DB_USER=admin' -e 'DB_PASS=admin' -e 'DB_NAME=todo' -p 5432:5432 sameersbn/postgresql:9.4-4```

To run a container for the application:

```docker build -t todoapp .```

```docker run -d -p 5000:5000 -e 'APP_SETTINGS=config.StagingConfig' -e 'PYTHONPATH=/todoapp-flask' --link postgresql:postgres --name todo todoapp```

Or, with docker-compose:

```docker-compose up```

# Debug Tips
## How to access postgres database using psql.
* Step 1 -- Login to postgres container:  

 ```docker exec -i -t postgresql /bin/bash```

* Step 2 -- Login to postgres using psql.

```psql -U admin -h 127.0.0.1 todo```

