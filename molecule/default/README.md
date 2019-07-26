# Molecule test examples

```shell
DOCKER_IMG="geerlingguy/docker-debian10-ansible:latest" molecule test
DOCKER_IMG="geerlingguy/docker-debian9-ansible:latest" molecule test

DOCKER_IMG="ubuntu:cosmic" DOCKER_PRE_BUILD_IMG=false molecule test
DOCKER_IMG="geerlingguy/docker-ubuntu1804-ansible:latest" molecule test
DOCKER_IMG="geerlingguy/docker-ubuntu1604-ansible:latest" molecule test

DOCKER_IMG="geerlingguy/docker-centos7-ansible:latest" DOCKER_CMD="/usr/sbin/init" molecule test
```
