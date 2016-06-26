# Ansible Role for PostgreSQL

<span class="badges" align="center">
[![Build Status](https://travis-ci.org/dgnest/ansible-role-postgresql.svg)](https://travis-ci.org/hadenlabs/ansible-role-postgresql)
[![Stories in Ready](https://badge.waffle.io/dgnest/ansible-role-nodejs.svg?label=ready&title=Ready)](http://waffle.io/hadenlabs/ansible-role-postgresql)
[![GitHub issues](https://img.shields.io/dgnest/issues/dgnest/ansible-role-nodejs.svg)](https://github.com/hadenlabs/ansible-role-postgresql/issues)
[![GitHub license](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square)](LICENSE)
</span>


A role for deploying and configuring [PostgreSQL][link-postgresql]
and extensions on unix hosts using [Ansible][link-ansible]
It can additionally be used as a playbook for quickly provisioning hosts.
Vagrant machines are provided to produce a boxed install of PostgreSQL or a VM for integration testing.

## Supports

Supported PostgreSQL versions:

- PostgreSQL 9.4
- PostgreSQL 9.3

Supported targets:
- Ubuntu 14.04 LTS "Trusty Tahr"
- Ubuntu 12.04 LTS "Precise Pangolin"
- Debian (untested)
- RedHat (untested)

## Requirements

 - Linux
   - none
 - OSX
   - [Homebrew][link-brew] must be installed.


## Role Variables

The default role variables in `defaults/main.yml` are:

    ```yaml
    # PostgreSQL
    postgresql_version: 9.4
    postgresql_listen_addresses:
      - '*'

    postgresql_databases:
      - name: 'test_data'
        port: 5432

    postgresql_users:
      - db: 'name_database'
        name: 'user'
        password: 'P@ssw0rd'
        priv: ALL
        role_attr_flags: SUPERUSER
    ```

## Dependencies

none

## Example Playbook

See the [examples](./examples/) directory.

To run this playbook with default settings, create a basic playbook like this:

    - hosts: servers
      roles:
         - postgresql

To install a specific version:

    - hosts: servers
      roles:
         - { role: luismayta.postgresql }


## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Credits

- [Luis Mayta][link-author]
- [All Contributors][link-contributors]

<!-- info repositories -->
[svg-travis]: https://travis-ci.org/dgnest/ansible-role-postgresql.svg
[link-travis]: https://travis-ci.org/hadenlabs/ansible-role-postgresql
[svg-waffle]: https://badge.waffle.io/dgnest/ansible-role-nodejs.svg?label=ready&title=Ready
[link-waffle]: http://waffle.io/hadenlabs/ansible-role-postgresql
[svg-issues]: https://img.shields.io/dgnest/issues/dgnest/ansible-role-nodejs.svg
[link-issues]: https://github.com/hadenlabs/ansible-role-postgresql/issues
<!-- info repositories -->

[link-postgresql]: http://www.postgresql.org/
[link-brew]: http://brew.sh/
[link-ansible]: http://www.ansibleworks.com/
<!-- Other -->
[link-author]: https://github.com/luismayta
[link-contributors]: contributors
