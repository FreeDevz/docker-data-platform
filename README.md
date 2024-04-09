# docker-data-platform
Refer to each directory's README file for Docker installation.
We chose this approach as this is more modular and easier to troubleshoot, rather than relying on one huge gigantic one docker compose file and lose track of the installation notes.

## Pre-requisites
```
Install Docker Desktop Version:
4.29.0 (145265)
Engine: 26.0.0
Compose: v2.26.1-desktop.1
Credential Helper: v0.8.1
Kubernetes: v1.29.2
```

### 1. Create User Defined Bridge
To start with, let's create the user defined network

```shell
docker network ls
docker network create my-network
docker network inspect my-network
```

### 2. Overview of Installation Order
Install in the following order:
1. minio
2. postgres and pgadmin (postgres client)
3. hive-metastore (hiveserver2 is optional)
4. trino
5. airflow