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