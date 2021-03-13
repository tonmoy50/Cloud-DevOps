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

## Resources
1. [How to copy docker images](https://stackoverflow.com/questions/23935141/how-to-copy-docker-images-from-one-host-to-another-without-using-a-repository)
