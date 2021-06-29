the following steps solved the problem for me.

remove docker:
```
$ sudo apt-get remove docker docker-engine
```
reinstall with
```
curl -sSL https://get.docker.com/ | sh
```
add user to a group:
```
sudo usermod -aG docker $USER
```
The `docker system prune` command removes all stopped containers, dangling images, and unused networks:
```
docker system prune -f
```
If you want to tag a docker image and push to the registry do the following:

```
$ docker image tag rhel-httpd:latest registry-host:5000/myadmin/rhel-httpd:latest
$ docker image push registry-host:5000/myadmin/rhel-httpd:latest
```
```
# List all containers (only IDs)
docker ps -aq
# Stop all running containers
docker stop $(docker ps -aq)
# Remove all containers
docker rm $(docker ps -aq)
# Remove all images
docker rmi $(docker images -q)
```
To find all the containers and stop and remove them:
```
docker ps -a
docker stop <container_id>
docker rm -f <container_id>
```
To find all the images and stop and remove them:
```
docker images
docker stop <image_id>
docker rmi -f <image_id>
```

## Resources
1. [How to copy docker images](https://stackoverflow.com/questions/23935141/how-to-copy-docker-images-from-one-host-to-another-without-using-a-repository)
2. [How To Remove Docker Containers, Images, Volumes, and Networks](https://linuxize.com/post/how-to-remove-docker-images-containers-volumes-and-networks/#:~:text=%2D%2Drm%20flag.-,Removing%20one%20or%20more%20containers,containers%20you%20want%20to%20remove.)
3. [docker push](https://docs.docker.com/engine/reference/commandline/push/)
