DEMO 3
=====================

Build Container Images

Instructions
------------

Start the VS 2017 solution "DockerVoter"

In the project, there is a "src" folder, navigate to the "basic" project.

Select to Pulish the webapplication, it should get you files in to the "docker\basic\site" folder in the root.

From the "docker/basic" folder, open and look at the "dockerfile"

Navigat to this folder with a CMD, and start a docker build
Try to run commands
```console
docker build -t basic:1.0 .
```

Now list to see the new image and try to start it, next check for the IP and navigate to it with a browser.
```console
docker images
docker run -d -p 80:80 --name bas01 basic:1.0
docker inspect bas01
```

Next, update the code in the repository for the basic site under the "src" folder.
Chande the text:
```console
    <img src="images/o.gif">    
    <p>Great success</p>    
```
To:
```console    
    <img src="images/c.gif">    
    <p>Catastrophic failure</p>
```

Do a new publish of the site and rebuild it with docker as follow.
```console
docker build -t basic:1.1 .
```

Stop the previous conatiner and the start the new image.
```console
docker stop bas01
docker run -d -p 80:80 --name bas02 basic:1.1
docker inspect bas02
```