# Install Docker Minio
1. Create data directory for minio to bind volume on
2. Add to user-defined-bridge "my-network"
3. Install with docker run command
```shell
export DOCKER_DATA_PLATFORM_HOME=/Users/androwijaya/devspace/IdeaProjects/docker-data-platform
export MINIO_HOME_DIR=$DOCKER_DATA_PLATFORM_HOME/minio

mkdir -p $MINIO_HOME_DIR/data
echo "Data to be mounted at $MINIO_HOME_DIR/data"

docker run -d \
   --net my-network \
   -p 9000:9000 \
   -p 9001:9001 \
   --name minio \
   -v $MINIO_HOME_DIR/data:/data \
   -e "MINIO_ROOT_USER=minio" \
   -e "MINIO_ROOT_PASSWORD=minio123" \
   quay.io/minio/minio server /data --console-address ":9001"
```


Go to WebUI at http://localhost:9001/login

### Useful Docker Commands
Force remove container
```shell
docker rm -f minio
```
Force remove image
```shell
docker rmi -f quay.io/minio/minio:latest
```



