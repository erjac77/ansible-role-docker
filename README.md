# Ansible Role: Docker

An Ansible role to install Docker CE on various Linux distributions.

## Requirements

#### Supported distributions

| Debian | Ubuntu |
| --- | --- |
| Buster 10<br> | Cosmic 18.10 |
| Stretch 9 (stable) /<br>Raspbian Stretch | Bionic 18.04 (LTS) |
| | Xenial 16.04 (LTS) |

## Installation

```
ansible-galaxy install erjac77.docker
```

## Role Variables

```yaml
# Channel ("stable", "edge", "testing" or "nightly")
docker_channel: stable
# State ("present", "latest")
docker_state: present

# Test container infos
docker_test_container_name: hello-world
docker_test_container_image: hello-world

# List of users to be added to the docker group
docker_users: ["{{ lookup('env', 'USER') }}"]

# Flag to configure Docker to start on boot
docker_start_on_boot: true
```

## Dependencies

None.

## Example Playbook

```yaml
- name: Install Docker
  hosts: localhost
  become: yes

  roles:
    - erjac77.docker
```

## License

Apache 2.0

## Author Information

Eric Jacob ([@erjac77](https://github.com/erjac77))
