# Database Image

## MySQL image

```
// Example creation of MySQL DB running on Docker
docker pull mysql:8.0.25
docker run --name local_service_dashboard -p 3306:3306 -e MYSQL_ROOT_PASSWORD=admin1234 -d mysql:8.0.25

// Example MySQL Workbench setup:
Connection Name: local_service_dashboard
Hostname: 127.0.0.1
Port: 3306
Username: root
```

## Mongo DB with network option

```
// Get the mongo from docker hub
docker pull mongo

// Start the image in detached mode
docker run -d --name mongodb mongo

// Get info about the container in a dictionary form - you can get IP address for example
docker container inspect mongodb

// Create container network (IP are automatically resolved)
docker run --network my_network ...

// Stop container 
docker stop mongodb

// Remove all stopped containers
docker container prune

// Create a docker network
docker network create network-name

// Inspect all existing networks
docker network ls

// Run the container with network option
docker run -d --name mongodb --network network-name mongo
```
