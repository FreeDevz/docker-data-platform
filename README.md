# docker-data-platform
Refer to each directory's README file for Docker installation.

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