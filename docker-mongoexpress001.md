# docker-mongoexpress001

****************************************
Creating Network for containers
docker network create mongo-nw001
docker network ls

****************************************

Creating mongo-express container and attached network&mongo db
docker run -d --network mongo-nw001 --name mongoexpress001 -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=mongoadmin -e ME_CONFIG_MONGODB_ADMINPASSWORD=secret -e ME_CONFIG_MONGODB_SERVER=mongodb001 mongo-express
docker logs mongoexpress001 -f

docker run -d \
--network mongo-nw001 \
--name mongoexpress001 \
-p 8081:8081 \
-e ME_CONFIG_MONGODB_ADMINUSERNAME=mongoadmin \
-e ME_CONFIG_MONGODB_ADMINPASSWORD=secret \
-e ME_CONFIG_MONGODB_SERVER=mongodb001 \
mongo-express
docker logs mongoexpress001 -f

##windows cmd/powershell 
docker run -d `
--network mongo-nw001 `
--name mongoexpress001 `
-p 8081:8081 `
-e ME_CONFIG_MONGODB_ADMINUSERNAME=mongoadmin `
-e ME_CONFIG_MONGODB_ADMINPASSWORD=secret `
-e ME_CONFIG_MONGODB_SERVER=mongodb001 `
mongo-express
docker logs mongoexpress001 -f

