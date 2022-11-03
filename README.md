[![CI](https://github.com/de-it-krachten/ansible-role-postgres_docker/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-postgres_docker/actions?query=workflow%3ACI)


# ansible-role-postgres_docker

Setup Postgres database in Docker
<basic role description>



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
- AlmaLinux 8<sup>1</sup>
- AlmaLinux 9<sup>1</sup>
- Debian 10 (Buster)<sup>1</sup>
- Debian 11 (Bullseye)<sup>1</sup>
- Ubuntu 18.04 LTS<sup>1</sup>
- Ubuntu 20.04 LTS<sup>1</sup>
- Ubuntu 22.04 LTS<sup>1</sup>
- Fedora 35<sup>1</sup>
- Fedora 36<sup>1</sup>
- Alpine 3<sup>1</sup>
- Docker dind (CI only)

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Postgres version
postgres_version: 12

# Postgres docker image
postgres_image: postgres:{{ postgres_version }}

# Name of the postgres container
postgres_container_name: postgres

# Name of the postgres container
postgres_hostname: postgres

# Directory with compose file
postgres_compose_dir: /export/docker/postgres/compose

# Directory with data files
postgres_data_dir: /data/docker/postgres/data

# External port
postgres_port: 5432

# Database name & credentials
postgres_database: db1
postgres_username: user1
postgres_password: password1
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'postgres_docker'
  hosts: all
  become: "yes"
  tasks:
    - name: Include role 'postgres_docker'
      ansible.builtin.include_role:
        name: postgres_docker
</pre></code>
