# Part 5

Linking containers and starting with a property file.

### Docker commands

Talk about and try:

* `docker build`
* `docker run`

### Build Your Runnable Jar

* `mvn clean package`

### Build your image

* Build your new image: `docker build -t dockerlab/db-service-java:part5 .`

### Start Container from Custom Image, link to MySQL and start using property file

* Make sure your database is running from Part 2.
* `docker run -t -i --link dockerlab-mysql:db --env-file ./dev.env.properties dockerlab/db-service-java:part5`
* `docker ps` Container is running, and `docker logs container_id` is now looking fine.
It's possible to see that the properties have been resolved.

