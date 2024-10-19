ansible-role-vaultwarden
=========

[![Lint and Test](https://github.com/guerzon/ansible-role-vaultwarden/workflows/Lint%20and%20Test/badge.svg)](https://github.com/guerzon/ansible-role-vaultwarden/actions?query=workflow%3ALint%20and%20Test)
[![Release](https://github.com/guerzon/ansible-role-vaultwarden/workflows/Release/badge.svg)](https://github.com/guerzon/ansible-role-vaultwarden/actions?query=workflow%3ARelease)

Install and manage your Vaultwarden instances using Ansible.

Requirements
------------

None

Role Variables
--------------

Specify the web vault and API server versions:

```yaml
web_vault_version: "2024.6.2c-1.7"
api_server_version: "1.32.2-2.2"
```

The data directories can also be specified as follows:

```yaml
data_folder: "/var/lib/vaultwarden"
web_vault_folder: "/usr/share/vaultwarden/web-vault"
```

More configuration options to be added.

Dependencies
------------

None

Example Playbook
----------------

Minimal installation example using a SQLite database:

```yaml
- hosts: all
  roles:
    - vaultwarden
```

License
-------

[MIT](./LICENSE)

Author Information
------------------

This Ansible role is managed by [Lester Guerzon](https://medium.com/@linuxheadafterhours).
