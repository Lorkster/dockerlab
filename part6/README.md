# Part 6

Pushing and pulling from Docker Hub.

### Docker commands

Talk about and try:

* `docker push`
* `docker pull`

### Pushing and image to Docker Hub

Start with registering an account on Docker Hub. Pass along either your username or the email address used for registering and you'll be added to the FindOut organization

* Move to the part5 directory.
* Push the previously build image to Docker Hub: `docker push findout/db-service-java:part5`
* The repository needs to exist before pushing and the name standard is `organization\repository_name:tag`
* Try a pull: `docker pull findout/db-service-java:part5`
* Start Kitematic and check `My Repos`. It's also possible to pull using that GUI, but in this case make sure to select a tag (since latest doesn't exist).
