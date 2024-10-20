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

Refer to the defaults file (`defaults/main.yml`) for the complete details. The following is an example configuration.

Specify the web vault and API server versions, and run Vaultwarden as a specific user:

```yaml
web_vault_version: "2024.6.2c-1.7"
api_server_version: "1.32.2-2.2"
appuser: "vault"
```

Specify the database settings:

```yaml
database_url: "postgresql://appuser:SecurePassword@192.168.100.100/vaultwardenprod"
```

Configure push notifications:

```yaml
push_enabled: "true"
push_installation_id: "CHANGEME"
push_installation_key: "CHANGEME"
```

General settings:

```yaml
domain: "https://pass.homelabnet.lcl"
signups_allowed: "true"
signups_verify: "true"
signups_domains_whitelist: "homelabnet.lcl"
invitations_allowed: "true"
invitation_org_name: "HomeLab Corp"
```

Advanced settings:

```yaml
admin_token: "CHANGEME"
disable_admin_token: "false"
```

Ensure emails are sent:

```yaml
smtp_host: "smtp.gmail.com"
smtp_from: "vaultadmin@homelabnet.lcl"
smtp_from_name: "Vault Administrator"
smtp_username: "tadmin@homelabnet.lcl"
smtp_password: "SecurePassword"
smtp_security: "starttls"
```

Set custom listening port:

```yaml
rocket_port: "5000"
```

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

Specify the domain name and custom Rocket port:

```yaml
- hosts: all
  vars:
    domain: "https://vaultwarden.homelabnet.lcl"
    rocket_port: "8000"
  roles:
    - vaultwarden
```

Supported Platforms
-------

Currently, the following are supported. Additional distros will be supported in the future.

- Red Hat Enterprise Linux 9
- Rocky Linux 9
- Fedora 40

License
-------

[MIT](./LICENSE)

Author Information
------------------

This Ansible role is managed by [Lester Guerzon](https://medium.com/@linuxheadafterhours).
