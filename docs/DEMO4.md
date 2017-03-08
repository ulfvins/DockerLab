DEMO 4
=====================

Build Voting application with Docker

Instructions
------------

Start the VS 2017 solution "DockerVoter"

- Build and Publish all the projects
- Docker build all the images

navigate to the docker folder, and kickoff the builds:
```console   
docker build -t dockervoter-votes:1.0 .
docker build -t dockervoter-api:1.0 .
docker build -t dockervoter-result:1.0 .
```

Next login to a Docker regiter and push the images
```console   
docker login addlevelregistry-devaddlevelnet.azurecr.io -u <username> -p <password>

docker tag dockervoter-votes:1.0 addlevelregistry-devaddlevelnet.azurecr.io/dockervoter-votes
docker tag dockervoter-api:1.0 addlevelregistry-devaddlevelnet.azurecr.io/dockervoter-api
docker tag dockervoter-result:1.0 addlevelregistry-devaddlevelnet.azurecr.io/dockervoter-result

docker push addlevelregistry-devaddlevelnet.azurecr.io/dockervoter-votes
docker push addlevelregistry-devaddlevelnet.azurecr.io/dockervoter-api
docker push addlevelregistry-devaddlevelnet.azurecr.io/dockervoter-result
```

docker run -d --net=nat -p 1433:1433 --name vot01 dockervoter-votes:1.0
docker run -d --net=nat -p 5000:5000 --name api01 dockervoter-api:1.0
docker inspect api01

Invoke-RestMethod -Method Get -Uri http://<  Container IP  >:5000/api/vote/

docker run -d --net=nat --name res01 -p 4000:4000 -e VOTE_SERVICE_URL=http://<  Container IP  >:5000/api/vote/ dockervoter-result:01

