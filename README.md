# Microservices
Microservices architecture

java -jar target\accounts-0.0.1-SNAPSHOT.jar

mvn spring-boot:run

docker build . -t sharpedgeshadow/accounts:s4
||

docker build . -t username/accounts:s4

docker images
docker inspect image 460ec991007e(imageid)

docker run -p 8080:8080 sharpedgeshadow/accounts:s4(to run container just like new operator of our java)

//to run in detached mode so we will not able to see logs
docker run -d -p 8080:8080 sharpedgeshadow/accounts:s4

docker ps// to find all running container of docker
docker ps -a // all container with stopped status

docker start container_id // to start the container


---------------using buildpacks---------------
mvn spring-boot:build-image //told maven to create image for buildpacks

docker run -d -p 8080:8080 sharpedgeshadow/loans:s4 (to run container)

-----------------jib plugin----------
mvn compile jib:dockerBuild
docker run -d -p 9000:9000 sharpedgeshadow/cards:s4

-----------Command TO Push our local docker image to docker hub repository

docker image push docker.io/sharpedgeshadow/accounts:s4
docker image push docker.io/sharpedgeshadow/cards:s4
docker image push docker.io/sharpedgeshadow/loans:s4

-------------Docker compose ------
used to run and handle all microservices by single point

docker compose version

docker-compose.yml 

//start all microservice with single command using docker-compose
docker compose up -d (create container -d for detached mode)

docker compose down (close all container & delete the container )

//to prevent it from remove
docker compose stop

//to start the container
docker compose start


docker images \
docker image inspect image_id \
docker build rm image_name \
docker build -t image_name \
docker run -p hostport:containerport image_name \
docker ps \
docker ps -a \
docker container start container_id \
docker container pause container_id \
docker container unpause container_id \
docker container stop container_id \
docker container kill container_id \
docker container restart container_id \
docker container inspect container_id \
docker container logs container_id \
docker container logs -f container_id \
docker rm container_id \
docker container prune  \
docker image push container_registry/username:tag \
docker image pull container_registry/username:tag \
docker image prune \
docker container stats \
docker system prune \
docker rmi image_id \
docker login -u username \
docker logout \
docker history image_name \
docker exec -it container_id sh \
docker compose up \
docker compose down \

---------------15-factor cloud Methodology

one codebase one application \
API first \
Dependency Management \
Desgin Build release run\
Configuration , credentials & code\
LOgs\
Disposability\
Backing services\
Environment parity\
Administrative processes\
Port binding\
stateless processes\
concurrency\
Telemetry\
Authentication & Authorization\