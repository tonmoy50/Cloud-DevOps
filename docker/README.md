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

## Resources
1. [How to copy docker images](https://stackoverflow.com/questions/23935141/how-to-copy-docker-images-from-one-host-to-another-without-using-a-repository)
2. [How To Remove Docker Containers, Images, Volumes, and Networks](https://linuxize.com/post/how-to-remove-docker-images-containers-volumes-and-networks/#:~:text=%2D%2Drm%20flag.-,Removing%20one%20or%20more%20containers,containers%20you%20want%20to%20remove.)
