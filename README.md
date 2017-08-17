Certbot from Let's Encrypt
=========

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
- `{{ certbot_domains }}` is a comma-separated string of the domains you wish to create a certificate for. e.g.: 'myexample.com,myexample.net'
- `{{ certbot_email }}` is the notifications address that Certbot will use to send expiration notices.

Role variables
--------------

These are the variables that are passed with a brief description. For all default variables, take a look at `defaults/main.yml`

- `certbot_certificates_path`: The path where a symlink from the Let's Encrypt certificate(s) folder to the current server will be created.
- `certbot_current_server`: The current server which will use the certificate(s).
- ...

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
