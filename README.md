Ansible Role: Docker ECR Authentication
=======================================

An [Ansible Galaxy](https://galaxy.ansible.com/) role for configuring Docker for authentication with Amazon Elastic Container Registry.

Requirements
------------

- [Golang](https://golang.org/) 1.11+
- [Docker](https://www.docker.com/)

Role Variables
--------------

The following variables should be defined in projects that use this role:

| Variable              | Default | Description                                                            |
|-----------------------|---------|------------------------------------------------------------------------|
| `docker_ecr_registry` | *None*  | The AWS ECR host (e.g. `1234567890.dkr.ecr.eu-west-1.amazonaws.com`)   |
| `docker_ecr_users`    | *None*  | A list of usernames that will be configured for Docker ECR integration |

For example:

```
docker_ecr_registry: 1234567890.dkr.ecr.eu-west-1.amazonaws.com

docker_ecr_users:
  - ecr-user-1
  - ecr-user-2
```

Example Requirements File
-------------------------

```
- src: https://github.com/companieshouse/ansible-role-docker-ecr
  name: docker-ecr
```

License
-------

MIT
