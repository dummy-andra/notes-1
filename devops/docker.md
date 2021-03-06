# Docker
## Syntax
### docker container
Syntax  | Description
:---    | :---
docker container commit $CONTAINERID | save container as a new, custom image
docker container diff $CONTAINERID | display all files added to or removed from base image
docker container ls
docker container ls -a
docker container run alpine ls -l 
docker container run hello-world 
docker container run -it alpine /bin/sh 

### docker image
Syntax  | Description
:---    | :---
docker image build -t hello:v0.1 . | create docker image named "hello" with tag "v0.1" from contents of current directory
docker image inspect alpine
docker image ls
docker image pull alpine
docker image tag $IMAGEID $TAG | tag a container image

## Dockerfile
A Docker image consists of read-only **layers**, each of which represents a delta of the preceding layer and corresponds to a Dockerfile **instruction**. [[26](#sources)]
```dockerfile
FROM alpine
RUN apk update && apk add nodejs
COPY . /app
WORKDIR /app
CMD ["node","index.js"]
```
[[25](README.md#sources)]