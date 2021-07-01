## Prod Server Installation

### Docker Installation

Get and install docker via script for linux:

```
 curl -fsSL https://get.docker.com -o get-docker.sh
 sudo sh get-docker.sh
```

### Docker Compose Installation

For stable version download with `curl`, run the following command

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

If it fails then do the following

```
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

Check

```
docker-compose --version
```

If you want to install in python environment

```
sudo pip install docker-compose
```

To run docker-compose

```
docker-compose -f local.yml up --build -d
```

### Miniconda Installation

Go to this [url](https://docs.conda.io/en/latest/miniconda.html#linux-installers) and download the installer script for linux and run the following command:

```
bash Miniconda3-latest-Linux-x86_64.sh
```

# RHEL Docker Setup

```
# sudo yum remove docker docker-common docker-selinux docker-engine-selinux docker-engine docker-ce
# sudo yum install -y yum-utils device-mapper-persistent-data lvm2
# sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
# sudo yum install docker-ce
```

If the error persits

```
# yum-config-manager --enable REPOSITORY
# yum install docker
```

If the error comes again

```
# subscription-manager register
# subscription-manager list --available
# subscription-manager attach --pool=pool_id
# subscription-manager repos --enable=rhel-7-server-rpms
# subscription-manager repos –enable=rhel-7-server-extras-rpms
# sudo yum remove docker docker-common docker-selinux docker-engine-selinux docker-engine docker-ce
# sudo yum install -y yum-utils device-mapper-persistent-data lvm2
# sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
# sudo yum install docker-ce
# yum-config-manager --enable REPOSITORY
# yum install docker
# systemctl start docker.servic
```
