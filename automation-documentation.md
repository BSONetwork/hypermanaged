# Ansible

Ansible repositories should have:

- a `inventory.yml` file with all hosts, like this:

```
front-prod:
  hosts:
    web-prod-01: {}
    web-prod-02: {}
db-prod:
  hosts:
    db-prod-01: {}
    db-prod-02: {}
front-preprod:
  hosts:
    web-preprod-01: {}
    web-preprod-02: {}
db-prod:
  hosts:
    db-preprod-01: {}
    db-preprod-02: {}

front:
  children:
    front-prod
    front-preprod
db:
  children:
    db-prod
    db-preprod

prod:
  children:
    front-prod
    db-prod
preprod:
  children:
    front-preprod
    db-preprod
```


- a `site.yml` playbook calling roles, like this:

```
- hosts: front
  roles:
    - common
    - nginx
    - php
    - customer-specific-role

- hosts: db
  roles:
    - common
    - mariadb
```


- a `roles` directory with a `requirements.yml` for ansible-galaxy with global roles, like this

```
- src: git@git.example.com/ansible-roles/common.git
  scm: git
  version: main
- src: git@git.example.com/ansible-roles/nginx.git
  scm: git
  version: main
- src: git@git.example.com/ansible-roles/php.git
  scm: git
  version: main
- src: git@git.example.com/ansible-roles/mariadb.git
  scm: git
  version: main
```

and if needed specific roles for the targeted infrastructure.

Global roles can be imported or updated, from the root of the repository, with:

```
ansible-galaxy install -r requirements.yml -p roles --force
```

- a `.gitignore` file (or equivalent if you use an other versioning system) to ignore global roles in this repository, like this:

```
roles/*
!roles/customer-specific-roles
```

- variables can be put on `group_vars/<group_name>` and `host_vars/<host_name>`


Then we can deploy with:

```
ansible-playbook -i inventory.yml site.yml
```

We can deploy only in specific hosts with `--limit` (`-l`) or only specific tasks with `--tags` (`-t`) (with tags defined on tasks in the roles):

```
ansible-playbook -i inventory.yml site.yml -l front-preprod -t nginxvhosts
```

