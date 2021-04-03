Ansible Role: User_Setup
=========

Creates local accounts on server, including Ansible Service account.

Requirements
------------

The role does not require anyting to run on RHEL and its derivatives.

If desired, an existing Private key file for the Ansible Service account can be provided before role executes.

Role Variables
--------------
Available variables are listed below, along with default values (see `defaults/main.yml`):

```
ansible_service_user: myserviceuser

ansible_service_pass_enc: "encrypted-password-for-ansible-service-account"

ansible_service_account_key: "ssh-public-key-file"

regular_user: myuser

regular_pass_enc: "encrypted-password-for-regular-account"
```

`ansible_service_user` = (**Required**) Name of the Ansible Service user account

`ansible_service_pass_enc` = (**Required**) Encrypted password to be assigned to the Ansible Service user account. Use *mkpasswd --method=sha-512* to generate encrypted password string

`ansible_service_account_key` = (Optional) A previously created SSH Public key for assignment to the Ansible Service user account.

`regular_user` = (**Required**) Name of the regular user account

`regular_pass_enc` = (**Required**) Encrypted password to be assigned to the regular user account. Use *mkpasswd --method=sha-512* to generate encrypted password string

Role variables can be stored with the `hosts.yaml` file, or in the main variables file.

Dependencies
------------

None.

Example Playbook
----------------

``` yaml
    - hosts: servers
      roles:
         - mikepruett3.user_setup
```

License
-------

MIT / BSD

Author Information
------------------

Role created by [mikepruett3](https://github.com/mikepruett3) on [Github.com](https://github.com/mikepruett3)
