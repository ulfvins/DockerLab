DEMO 2
=====================

Basic Docker commands

Instructions
------------

List basic information
```console
docker info
docker version
```

Get images from DockerHub
Navigate to: https://hub.docker.com/r/microsoft or...
```console
docker search microsoft
docker pull microsoft/dotnet-samples:dotnetapp-nanoserver
```

Try to run commands
```console
docker --help
docker run --help
```

Run basic .NET core image
```console
docker run microsoft/dotnet-samples:dotnetapp-nanoserver
```

Inspect run history, clean up container runtime
```console
docker ps -a
docker inspect <container id>
docker rm <container id>
```

Start a new IIS Docker runtime with interaction
```console
docker run -it -p 80:80 microsoft/iis cmd
```
Look with process explorer, how the process structure looks like.
Start PowerShell, do you notice any difference.

In the console, change files
```console
del C:\inetpub\wwwroot\iisstart.htm
echo "Container Rocks" > C:\inetpub\wwwroot\index.html
```

Stop the container, get the name of the ID and save the changes.
```console
docker ps -a
docker commit <Container ID> modified-iis
```