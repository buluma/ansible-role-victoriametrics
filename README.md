# [victoria_metrics](#victoria_metrics)

Role for VictoriaMetrics

|GitHub|GitLab|Quality|Downloads|Version|Issues|Pull Requests|
|------|------|-------|---------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-victoria_metrics/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-victoria_metrics/actions)|[![gitlab](https://gitlab.com/buluma/ansible-role-victoria_metrics/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-victoria_metrics)|[![quality](https://img.shields.io/ansible/quality/)](https://galaxy.ansible.com/buluma/victoria_metrics)|[![downloads](https://img.shields.io/ansible/role/d/)](https://galaxy.ansible.com/buluma/victoria_metrics)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-victoria_metrics.svg)](https://github.com/buluma/ansible-role-victoria_metrics/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-victoria_metrics.svg)](https://github.com/buluma/ansible-role-victoria_metrics/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-victoria_metrics.svg)](https://github.com/buluma/ansible-role-victoria_metrics/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.victoriametrics
```


## [Role Variables](#role-variables)

The default values for the variables are set in `defaults/main.yml`:
```yaml
---
# defaults file for VictoriaMetrics
victoriametrics_repo_url: "https://github.com/VictoriaMetrics/VictoriaMetrics"
victoriametrics_download_url: "{{ victoriametrics_repo_url }}/releases/download/{{ victoriametrics_version }}/victoria-metrics-{{ victoriametrics_version }}.tar.gz"
victoriametrics_vmutils_download_url: "{{ victoriametrics_repo_url }}/releases/download/{{ victoriametrics_version }}/vmutils-{{ victoriametrics_version }}.tar.gz"
victoriametrics_version: "v1.28.0"
victoriametrics_system_user: "victoriametrics"
victoriametrics_system_group: "{{ victoriametrics_system_user }}"
victoriametrics_data_dir: "/var/lib/victoria-metrics/"
victoriametrics_service_args:
  storageDataPath: "{{ victoriametrics_data_dir }}"
victoriametrics_max_open_files: 2097152
victoriametrics_install_vmutil: false
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-victoria_metrics/blob/main/requirements.txt).


## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.co.ke/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-victoria_metrics/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|debian|all|
|el|8|
|fedora|all|
|opensuse|all|
|ubuntu|all|

The minimum version of Ansible required is 2.1, tests have been done to:

- The previous version.
- The current version.
- The development version.

## [Exceptions](#exceptions)

Some roles can't run on a specific distribution or version. Here are some exceptions.

| variation                 | reason                 |
|---------------------------|------------------------|
| Alpine | /bin/sh: sudo: not found |


If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-victoria_metrics/issues)

## [License](#license)

Apache-2.0

## [Author Information](#author-information)

[Michael Buluma](https://buluma.github.io/)
