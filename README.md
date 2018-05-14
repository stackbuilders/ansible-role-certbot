Certbot from Let's Encrypt
=========
[![Ansible Galaxy](https://img.shields.io/badge/role-stackbuilders.certbot-blue.svg)](https://galaxy.ansible.com/stackbuilders/certbot/)

This Ansible role creates one or more Let's Encrypt certificates using Certbot.

Requirements
------------

This role requires Ansible 2.3 or higher and the platform requirements are listed in the metadata file.

Install
------------

```sh
ansible-galaxy install stackbuilders.certbot
```

Getting started
------------

You need to define the following variables:
- `{{ certbot_domains }}` is a comma-separated string of the domains you wish to create a certificate for. e.g.: `'myexample.com,myexample.net'`
- `{{ certbot_email }}` is the notifications email address that Certbot will use to send expiration notices.

Role variables
--------------

For all default variables, take a look at [defaults/main.yml](defaults/main.yml)

Example playbook
----------------

```yaml
- hosts: webservers
  become: yes
  roles:
    - role: stackbuilders.certbot
      certbot_domains: 'mydomain.com'
      certbot_email: 'alerts@mydomain.com'
```

License
-------

MIT

Author Information
------------------

Stack Builders Inc.
