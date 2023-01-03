# Docker Commands

#### Remove docker all container and images

```
docker system prune
docker system prune -a
docker images -a
```

#### Remove image
```
docker ps -a
docker stop idnumber
docker rm idnumber
dokcer images
docker rmi idnumber


#### Remove unused images
```
docker image prune
```
#### Remove stopped containers.
```
docker container prune
```

#### Remove unused volumes
```
docker volume prune
```
#### Remove unused networks
```
docker network prune
```
#### Command to run all prunes:
```
docker system prune
```
