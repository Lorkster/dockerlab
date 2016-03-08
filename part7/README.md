# Part 7

Using Docker Compose.

### Docker commands

Talk about and try:

* `docker-compose build`
* `docker-compose up`
* `docker-compose logs`
* `docker-compose down`

### Docker Compose

There's a simple `docker-compose.yml` in the folder. It allows you to define several containers in a single definition and control them as a unit.

The file allows building and running of Part 2 (database) and Part 5 (database service) and links them together using the same mechanics we've done manually in previous parts.

* Build your images: `docker-compose build`.
* And then start, either in attached `docker-compose up` or detached `docker-compose up -d` mode.
* When using detached mode, you can then access the logs with `docker-compose logs` and pull it all down with `docker-compose down`.
* It's possible to start parts of a compose file by name. The `depends_on` definition makes sure that all needed parts are started anyway. In this instance you can start with `docker-compose up dockerlab-db-service-java`, which will also start the database.