Ansible Role: Docker ECR Authentication
=======================================

An [Ansible Galaxy](https://galaxy.ansible.com/) role for configuring Docker for authentication with Amazon Elastic Container Registry.

Requirements
------------

- [Golang](https://golang.org/) 1.11+

Role Variables
--------------

The following variables should be defined in projects that use this role:

| Variable              | Default | Description                                                            |
|-----------------------|---------|------------------------------------------------------------------------|
| `docker_ecr_registry` | *None*  | A list of usernames that will be configured for Docker ECR integration |
| `docker_ecr_users`    | *None*  | The AWS ECR host (e.g. `1234567890.dkr.ecr.eu-west-1.amazonaws.com`)   |

In addition, a `docker_ecr_environment` dictionary should be defined, comprising the following AWS access credentials:

| Variable                | Default | Description                                                          |
|-------------------------|---------|----------------------------------------------------------------------|
| `aws_access_key_id`     | *None*  | The AWS access key ID                                                |
| `aws_secret_access_key` | *None*  | The AWS secret access key                                            |
| `aws_default_region`    | *None*  | The AWS region (e.g. `eu-west-1`)                                    |

For example:

```
docker_ecr_registry: 1234567890.dkr.ecr.eu-west-1.amazonaws.com
  
docker_ecr_users:
  - ecr-user-1
  - ecr-user-2

docker_ecr_environment:
  aws_access_key_id: AAAABBBBCCCCDDDD1111
  aws_secret_access_key: abcdefghijklmnopqrstuvwxyz1234567890!@£ 
  aws_default_region: eu-west-1
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

