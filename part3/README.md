# Part 3

Creating a Sun Java image and executing terminal commands.

### Docker commands

Talk about and try:

* `docker build`
* `docker run`
* `docker ps`
* `docker exec`

### Create a Custom Image

Create a custom Dockerfile based on `expertsystems/oracle-jdk8`

* Base image on java layer: `FROM expertsystems/oracle-jdk8`.
* Build your new image: `docker build -t findout/oracle-jdk8:latest .`

### Start Container from Custom Image

* Start in detached mode with tty active `docker run --name dockerlab-jdk8 -d -t dockerlab/oracle-jdk8`.
* `docker ps`
* Take a look in your container: `docker exec -it dockerlab-jdk8 bash`.
* `docker rm -f dockerlab-jdk8`
* Start a container and execute a single command `docker run -i -t dockerlab/oracle-jdk8 java -version`.
* Start a container and enter tty `docker run -i -t findout/oracle-jdk8`.
* Verify that nothing is running `docker ps`.
