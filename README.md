# ansible-nginxlog_exporter

ansible-nginxlog_exporter is an Ansible role to install and configure [prometheus-nginxlog-exporter](https://github.com/martin-helmich/prometheus-nginxlog-exporter).

It performs: 

* installation of the github release
* creation of dedicated user and group for exporter runs
* creation of dedicated folder for exporter configurations
* configuration of listen address/port and of namespaces to be exported
* installation, start and enable of a dedicated systemd unit

## Install
### Clone
```bash
git clone https://github.com/lgaggini/ansible-nginxlog_exporter.git
```
## Configuration

The configuration is done by vars listed and explained in [defaults/main.yml](https://github.com/lgaggini/ansible-nginxlog_exporter/blob/master/defaults/main.yml) file.

## Usage

```
- name: bootstrap an ubuntu cloud image for nginx
  hosts: webservers
  vars_files:
    - group_vars/nginxlog_exporter.yml

  roles:
    - { role: nginxlog_exporter, tags: ['nginxlog_exporter'] }
```

## Credits

Heavily inspired by [node_exporter Cloudalchemy ansible role](https://github.com/cloudalchemy/ansible-node-exporter).
