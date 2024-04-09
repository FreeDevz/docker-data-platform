# docker-data-platform
Refer to each directory's README file for Docker installation.

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
2. hive-metastore (hiveserver2 is optional)
3. trino
4. airflow