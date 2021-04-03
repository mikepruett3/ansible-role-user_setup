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
user_account: myuseraccount

user_pass_enc: "encrypted-password-for-user-account"

user_account_key: "ssh-public-key-file"

key_repository: "/path/to/key/repo/"

```

`user_account` = (**Required**) Name of the user account to create

`user_pass_enc` = (**Required**) Encrypted password to be assigned to the user account. Use *mkpasswd --method=sha-512* to generate encrypted password string

`user_account_key` = (Optional) A previously created SSH Public key for assignment to the user account.

`key_repository` = (**Required**) Path to where to store the new Public and Private SSH keys

Role variables can be stored with the `hosts.yaml` file, or in the main variables file.

Dependencies
------------

None.

Example Playbook
----------------

``` yaml
    - hosts: servers
      roles:
         - role: mikepruett3.user_setup
           vars:
             user_account: myuser
             user_pass_enc: "encrypted-password"
             user_account_key: "ssh-public-key-file"
             key_repository: "/path/to/key/repo/"
```

License
-------

MIT / BSD

Author Information
------------------

Role created by [mikepruett3](https://github.com/mikepruett3) on [Github.com](https://github.com/mikepruett3)
