## Kroid/ansible-common-role

Base role for everything:
* install python2
* install common packages
* add public ssh keys
* config ssh, hostname, locale


Tested on *ubuntu 16.04* and *ansible 2.2.1*.

#### Installation

1. Create an `requirements.yml` file:

```
---
- src: https://github.com/Kroid/ansible-common-role.git
```

2. Install requirements:

```
ansible-galaxy install -r requirements.yml
```

3. Change `authorized_key_urls` variable.
4. Define `host_name` variable.


#### Tips

* The role requires `gather_facts: False` in playbook:

```
- hosts: all
  gather_facts: False
  roles:
    - common
```

* example `ansible.cfg`:

```
[defaults]
retry_files_enabled = False
roles_path = roles
```