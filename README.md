# Ansible Role: VictoriaMetrics

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![debian-9](https://img.shields.io/badge/debian-9.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![debian-10](https://img.shields.io/badge/debian-10.x-orange?style=flat&logo=debian)](https://www.debian.org/

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-victoriametrics?style=flat)](https://github.com/OnkelDom/ansible-role-victoriametrics/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-victoriametrics.svg?style=flat)](https://github.com/OnkelDom/ansible-role-victoriametrics/tags)

## Description

Deploy [victoriametrics](https://github.com/victoriametrics/victoriametrics) monitoring system using ansible.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` | {} | Proxy environment variables |
| `victoriametrics_version` | 1.57.1 | victoriametrics package version. Also accepts `latest` as parameter. Only victoriametrics 2.x is supported |
| `victoriametrics_config_dir` | /etc/victoriametrics | Path to directory with victoriametrics configuration |
| `victoriametrics_data_dir` | /var/lib/victoriametrics | Path to directory with victoriametrics database |
| `victoriametrics_binary_install_dir` | /usr/local/bin | Path to directory with victoriametrics binaries |
| `victoriametrics_system_user` | prometheus | victoriametrics system user |
| `victoriametrics_system_group` | victoriametrics | victoriametrics system group |
| `victoriametrics_limit_nofile` | 16384 | set nofile limit in systemd unit |
| `victoriametrics_web_listen_address` | "0.0.0.0" | Address on which victoriametrics will be listening |
| `victoriametrics_web_listen_port` | 8428 | Port on which victoriametrics will be listening |
| `victoriametrics_log_level` | warn | Set loglevel |
| `victoriametrics_log_format` | json | Set logformat |
| `victoriametrics_prometheus_config` | {} | define prometheus config |
| `victoriametrics_config` | [] | define victoriametrics environment variables - [List Flags](https://github.com/VictoriaMetrics/VictoriaMetrics/blob/master/docs/Single-server-VictoriaMetrics.md#list-of-command-line-flags) |

## Example

### Playbook

```yaml
---
- hosts: all
  roles:
  - onkeldom.victoriametrics
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
