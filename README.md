Ansible Role: Docker ECR Authentication
=======================================

An [Ansible Galaxy](https://galaxy.ansible.com/) role for configuring Docker for authentication with Amazon Elastic Container Registry.

Role Variables
--------------

The following variables should be defined in any project that uses this role:

| Variable          | Default | Description                                                            |
|-------------------|---------|------------------------------------------------------------------------|
| `docker_ecr_user` | *None*  | The username for the system account that will be using ECR with Docker |

In addition, an `ecr_environment` dictionary variable should be defined, comprising the following AWS access credentials:

| Variable                | Default | Description                                                          |
|-------------------------|---------|----------------------------------------------------------------------|
| `aws_registry_host`     | *None*  | The AWS ECR host (e.g. `1234567890.dkr.ecr.eu-west-1.amazonaws.com`) |
| `aws_access_key_id`     | *None*  | The AWS access key ID                                                |
| `aws_secret_access_key` | *None*  | The AWS secret access key                                            |
| `aws_default_region`    | *None*  | The AWS region (e.g. `eu-west-1`)                                    |

For example:

```
docker_ecr_user: ecr-user

ecr_environment:
  aws_registry_host: 1234567890.dkr.ecr.eu-west-1.amazonaws.com
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

