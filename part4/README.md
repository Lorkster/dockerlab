# Part 4

Creating a Sun Java image and adding a runnable jar to it.

### Docker commands

Talk about and try:

* `docker build`
* `docker run`
* `docker ps`
* `docker exec`
* `docker stop`

### Build Your Runnable Jar

* `mvn clean package`

### Create a Custom Image

Create a custom Dockerfile based on expertsystems/oracle-jdk8

* Base image on mysql layer: `FROM expertsystems/oracle-jdk8`.
* Add environment variable `VERTICLE_FILE` and set it to `db-service-java-1.0-SNAPSHOT-fat.jar`.
* Add environment variable `VERTICLE_HOME` and set it to `/usr/verticles`.
* `COPY` your fat jar to `VERTICLE_HOME`.
* Set the image `WORKDIR` to `VERTICLE_HOME`.
* Add your entrypoint for the image: `ENTRYPOINT ["sh", "-c"]`.
* Set the command that starts the fat jar: `CMD ["java -jar $VERTICLE_FILE -ha"]`.
`CMD` sets the default arguments for the `ENTRYPOINT`
* Build your new image: `docker build -t dockerlab/db-service-java:part4 .`

### Start Container from Custom Image

* `docker run -d findout/db-service-java:part4`
* `docker ps` Container is running, but `docker logs container_id` will show errors.
* `docker kill container_id` and contintue in Part 5. 

