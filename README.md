# ANSIBLE ROLE: DOCKER

An Ansible role to install Docker on various Linux distributions.

_**Note:** At the moment, Ubuntu is the only platform supported by this role._

## REQUIREMENTS

* Ubuntu >= 14.04
* 64-bit Linux installation
* Linux kernel >= 3.10

## INSTALLATION

#### USING _ANSIBLE GALAXY_:

```
ansible-galaxy install erjac77.docker
```

#### USING _GIT CLONE_:

Clone this repository inside the `roles/` subdirectory of your playbook or inside one of the additional directories specified by the `roles_path` setting in `ansible.cfg`.

```
git clone https://github.com/erjac77/ansible-role-docker.git erjac77.docker
```

## ROLE VARIABLES

```
---

# Default package name (docker-engine)
docker_pkg_name: docker-engine

# Test container infos
docker_test_container_name: hello-world
docker_test_container_image: hello-world

# List of users to be added to the docker group
docker_group_members: [ "{{ lookup('env', 'USER') }}" ]

# Flag to enable UFW forwarding
docker_ufw_enable_forwarding: false
# Default UFW forward policy
docker_ufw_default_forward_policy: ACCEPT
# UFW rule to allow incoming connections on the Docker port
docker_ufw_rules:
  - { rule: allow, to_port: 2376, protocol: tcp }

# Flag to configure Docker to start on boot
docker_start_on_boot: true
```

### UBUNTU VARIABLES

```
---

# Flag to install linux-image-extra-* kernel packages
docker_install_linux_image_extras: true

# APT id and keyserver
docker_apt_key_id: 58118E89F3A912897C070ADBF76221572C52609D
docker_apt_key_keyserver: hkp://p80.pool.sks-keyservers.net:80
```

## DEPENDENCIES

None.

## EXAMPLE PLAYBOOK

```
---

- name: Install Docker
  hosts: localhost
  become: yes

  roles:
    - erjac77.docker
```

## LICENSE

Apache 2.0

## AUTHOR INFORMATION

Eric Jacob ([@erjac77](https://github.com/erjac77))