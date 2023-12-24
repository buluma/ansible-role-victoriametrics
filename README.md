# Ansible role [victoriametrics](https://galaxy.ansible.com/ui/standalone/roles/buluma/victoriametrics/documentation)

Ansible role for installing and configuring victoriametrics storage backend

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-victoriametrics/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-victoriametrics/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-victoriametrics.svg)](https://github.com/buluma/ansible-role-victoriametrics/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-victoriametrics.svg)](https://github.com/buluma/ansible-role-victoriametrics/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-victoriametrics.svg)](https://github.com/buluma/ansible-role-victoriametrics/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/victoriametrics)](https://galaxy.ansible.com/ui/standalone/roles/buluma/victoriametrics/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-victoriametrics/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  vars:
    victoriametrics_version: 1.82.0

  pre_tasks:
    - name: Update apt cache.
      apt: update_cache=yes cache_valid_time=600
      when: ansible_os_family == 'Debian'
      changed_when: false

  roles:
    - role: buluma.victoriametrics
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-victoriametrics/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-victoriametrics/blob/master/defaults/main.yml):

```yaml
---
proxy_env: {}
victoriametrics_version: 1.57.1
victoriametrics_web_listen_address: 0.0.0.0
victoriametrics_web_listen_port: 8428
victoriametrics_binary_install_dir: /usr/local/bin
victoriametrics_system_user: "{{ victoriametrics_user | default('prometheus') }}"
victoriametrics_system_group: "{{ victoriametrics_group | default('prometheus') }}"
victoriametrics_data_dir: /var/lib/victoriametrics
victoriametrics_config_dir: /etc/victoriametrics
victoriametrics_log_level: warn
victoriametrics_log_format: json
victoriametrics_prometheus_config: {}
victoriametrics_limit_nofile: 16384
victoriametrics_config:
  storageDataPath: "{{ victoriametrics_data_dir }}"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-victoriametrics/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-victoriametrics/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Debian](https://hub.docker.com/repository/docker/buluma/debian/general)|all|
|[Fedora](https://hub.docker.com/repository/docker/buluma/fedora/general)|all|
|[EL](https://hub.docker.com/repository/docker/buluma/enterpriselinux/general)|all|
|[Ubuntu](https://hub.docker.com/repository/docker/buluma/ubuntu/general)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-victoriametrics/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-victoriametrics/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-victoriametrics/blob/master/LICENSE).

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)


Template inspired by [Robert de Bock](https://github.com/robertdebock)
