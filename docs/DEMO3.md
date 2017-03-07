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