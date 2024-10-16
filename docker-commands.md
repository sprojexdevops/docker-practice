## List of all running containers
    docker ps

## list of all containers irrespective of the state
    docker ps -a

## list only container IDs irrespective of the state
    docker ps -a -q

## list of images available in the server
    docker images

#### list only image IDs
    docker images -q

## download or pull the image
    docker pull <image name>:<version>

> add version to pull the image of a specifi version, else it can be ignored
#### example: 
* docker pull nginx         ---> pull the latest
* docker pull nginx:1.27

## create a container
    docker create <image name>:<version>

## start a container
    docker start <container id>

## stop a container
    docker stop <container id>

## remove a container
    docker rm <container id>
    
## forcing to remove a running container
    docker rm -f <container id>

## removing the image
    docker rmi <image id>

## remove all images
    docker rmi -f $(docker images -q)

## pull image, create and start the container with a single command

#### runs the container in foreground and terminal is locked
    docker run <image name>:<version>

#### runs the container in background or detach mode and terminal can be used
    docker run -d <image name>:<version>

## port forwarding -- mapping host port and container port
    docker run -d -p <host port>:<container port> <image name>:<version>

## get inside the container
    docker exec -it <conatiner id> bash

## get the full details of a container
    docker inspect <container id>

## get the logs of a container
    docker logs <conatiner id>

## naming a container -- if no name is specified a random name is given to a container
    docker run -d -p <host port>:<container port> --name <name>  <image name>:<version>

## rename an existing container
    docker rename <existing name> <new name>

## Removing all containers
    docker rm -f $(docker ps -a -q)

## build a custom image
    docker build -t <name for image>:<version> .

## pushing the image to docker hub

#### login to docker hub account, if not already done
    docker login -u <username>

#### tag the custom image
    docker tag <name of custom image>:<version> <username>/<name of custom image>:<version>

* name of the custom image in local and docker hub can be same or different

#### push the image
    docker push <username>/<name of custom image>:<version>

## Use LABEL to filter the specific images
    docker images -f "label=<key>=<value>"
#### example
*   docker images -f "label=author=John"