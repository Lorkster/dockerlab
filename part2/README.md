# Part 2

Building a custom Docker image.

### Docker commands

Talk about and try:

* `docker build`
* `docker run`
* `docker ps`
* `docker exec`
* `docker stop`

### Create a Custom Image

Create a custom Dockerfile based on mysql:5.7

* Base image on mysql layer: `FROM mysql:5.7`.
* Add environment variable: `ENV MYSQL_ROOT_PASSWORD dockerlab_pw` and the other ones needed.
* Expose `3306` for future use.
* `COPY` the sql init script to the entrypoint initdb.
* If on OSX, `COPY` the needed bash script and `chmod` it, to modify the image entrypoint.
* Build your new image: `docker build -t dockerlab/mysql:latest .`

### Start Container from Custom Image

* `docker run -p 3306:3306 --name dockerlab-mysql -d dockerlab/mysql:latest .`
* `docker ps`
* Take a look in your container: `docker exec -it dockerlab-mysql bash`
* Access using your MySQL tool of choice.
* `docker rm -f dockerlab-mysql`
 
### Add a Volume for Data Persistence 

Data will be lost if container is removed. Linking in a volume is one way to solve that.

* `docker run -p 3306:3306 --name dockerlab-mysql -v /path/to/my/data:/var/lib/mysql -d dockerlab/mysql:latest .`
* Try removing the container and starting it again. Verify schema and data.

