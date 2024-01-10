# Docker Workshop By RBK

> Simple example of a dockerized Nodejs/Mongodb app

## Quick Start.

```bash
##########################################################################################
########## Manage the project using the Docker Compose CLI (Nodejs & mongodb)  ###########
##########################################################################################

# Run in Docker
docker-compose up

# To build
docker-compose build

# Tear down
docker-compose down

#  build and Run in background mode  (-d) 
docker-compose up -d --build 

#################################################################################
########## Manage the project using the Docker CLI (Nodejs & mongodb) ###########
#################################################################################

# Create a network:
docker network create docker-workshop-network

# Create a volume:
docker volume create db

# Run the mongodb container:
docker run -d \
    --name docker-workshop-mongodb \
    --restart always \
    -p 27018:27017 \
    --network docker-workshop-network \
    -v db:/data/db \
    mongo:latest

# Build the Docker image:
docker build -t docker-workshop-app .


# Run the app container:
docker run -d --name docker-workshop-app \
    -p 3001:3000 \
    --network=docker-workshop-network \
    --restart=always \
    docker-workshop-app


#######################################################################
########## Manage the project using the Docker CLI (Nodejs) ###########
#######################################################################

# Build the Docker image:
docker build -t docker-workshop-app .

# Run the app container:
docker run -d --name docker-workshop-app \
     -p 3001:3000 \
     docker-workshop-app

# Run the mongodb container (simple command): 
 docker run -d -p 27018:27017 mongo:latest



# Show running containers:
docker ps

# Show all images:
docker images
    
```
