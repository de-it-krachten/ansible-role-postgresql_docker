[![CI](https://github.com/de-it-krachten/ansible-role-postgresql_docker/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-postgresql_docker/actions?query=workflow%3ACI)


# ansible-role-postgresql_docker

Setup PostgreSQL database in Docker



## Dependencies

#### Roles
None

#### Collections
- community.general
- community.docker

## Platforms

Supported platforms

- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- RockyLinux 8<sup>1</sup>
- RockyLinux 9<sup>1</sup>
- OracleLinux 8<sup>1</sup>
- OracleLinux 9
- AlmaLinux 8<sup>1</sup>
- AlmaLinux 9<sup>1</sup>
- Debian 10 (Buster)<sup>1</sup>
- Debian 11 (Bullseye)<sup>1</sup>
- Ubuntu 18.04 LTS<sup>1</sup>
- Ubuntu 20.04 LTS<sup>1</sup>
- Ubuntu 22.04 LTS<sup>1</sup>
- Fedora 36<sup>1</sup>
- Fedora 37<sup>1</sup>
- Alpine 3<sup>1</sup>
- Docker dind (CI only)

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Database name & credentials
# postgresql_database: db1
# postgresql_username: user1
# postgresql_password: password1

# External port
postgresql_port: 5432

# Postgres version
postgresql_version: 12

# Postgres docker image
postgresql_image: postgres:{{ postgresql_version }}

# Name of the postgres container
postgresql_container_name: postgres

# Name of the postgres container
postgresql_hostname: postgres

# Directory with compose file
postgresql_compose_dir: /export/docker/postgres/compose

# Directory with data files
postgresql_data_dir: /export/docker/postgres/data
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'postgresql_docker'
  hosts: all
  become: "yes"
  vars:
    postgresql_database: db1
    postgresql_username: user1
    postgresql_password: password1
  tasks:
    - name: Include role 'postgresql_docker'
      ansible.builtin.include_role:
        name: postgresql_docker
</pre></code>
