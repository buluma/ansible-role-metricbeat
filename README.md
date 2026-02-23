# [Ansible role metricbeat](#ansible-role-metricbeat)

Install and configure Metricbeat, manage Metricbeat modules.

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-metricbeat/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-metricbeat/actions)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-metricbeat/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-metricbeat)|[![downloads](https://img.shields.io/ansible/role/d/buluma/metricbeat)](https://galaxy.ansible.com/buluma/metricbeat)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-metricbeat.svg)](https://github.com/buluma/ansible-role-metricbeat/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-metricbeat/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
  - become: true
    gather_facts: true
    hosts: all
    name: Converge
    roles:
      - metricbeat_elasticsearch_password: My-P@s5w0rd.
        metricbeat_modules:
          - name: system
            state: enabled
        role: buluma.metricbeat
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-metricbeat/blob/master/molecule/default/prepare.yml):

```yaml
---
  - become: true
    gather_facts: false
    hosts: all
    name: Prepare
    roles:
      - role: buluma.bootstrap
      - role: buluma.core_dependencies
      - role: buluma.elastic_repo
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-metricbeat/blob/master/defaults/main.yml):

```yaml
---
metricbeat_elasticsearch_hosts:
  - http://localhost:9200
metricbeat_elasticsearch_password: ""
metricbeat_elasticsearch_username: elastic
metricbeat_kibana_host: http://localhost:5601
metricbeat_modules: []
metricbeat_version: 7.17.6
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-metricbeat/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.core_dependencies](https://galaxy.ansible.com/buluma/core_dependencies)|[![Build Status GitHub](https://github.com/buluma/ansible-role-core_dependencies/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-core_dependencies/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-core_dependencies/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-core_dependencies)|
|[buluma.elastic_repo](https://galaxy.ansible.com/buluma/elastic_repo)|[![Build Status GitHub](https://github.com/buluma/ansible-role-elastic_repo/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-elastic_repo/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-elastic_repo/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-elastic_repo)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-metricbeat/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Amazon](https://hub.docker.com/r/buluma/amazonlinux)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|
|[Kali](https://hub.docker.com/r/buluma/kalilinux)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-metricbeat/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-metricbeat/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

