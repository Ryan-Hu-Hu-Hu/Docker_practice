## Login 
`docker login`

# Image related
## List the image   
`docker image ls` 
## Remove the image 
`docker image rm REPOSITORY` or `docker image rm IMAGE_ID`
## Build the image 
`docker build -t DOCKER_USERNAME/REPO_NAME .`
## Push the image 
`docker push DOCKER_USERNAME/REPO_NAME`

# Container related
## List the container in use  
`docker ps`  
### List all containers  
`docker ps -a`  
### List all containers with name only  
`docker ps -a -q`  
## Kill the container  
`docker kill CONTAINER_ID`  
### Kill all the container
`docker rm $(docker ps -a -q)`  
### Kill all the container with force   
`docker rm $(docker ps -a -q) -f`  
## Copy file from local file system into container
`docker cp <src-path> <container>:<dest-path> `
## Copy file from container into local file system
`docker cp <container>:<src-path> <local-dest-path>`


