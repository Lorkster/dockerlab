# Part 1

### Docker commands

Talk about and try out:

* `docker-machine start`
* `docker-machine stop`
* `docker-machine env`
* `docker pull`
* `docker run`
* `docker ps`
* `docker logs`
* `docker stop`

### Pull and start MySQL

* `docker pull mysql:5.7`
* `docker run -p 3306:3306 --name dockerlab-mysql -e MYSQL_ROOT_PASSWORD=dockerlab_pw -e MYSQL_PASSWORD=dockerlab_pw -e MYSQL_USER=dockerlab -d mysql:5.7`
* `docker ps`
* `docker logs your_container_id`
* `docker stop your__container_id`

