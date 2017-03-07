DEMO 1
=====================

Installing Docker

Instructions
------------

Text:

See latet version of docker
```console
(Invoke-WebRequest -UseBasicParsing https://raw.githubusercontent.com/docker/docker/master/VERSION).Content.Trim()
```

Download Docker-For-Windows
```console
Navigate to: https://docs.docker.com/docker-for-windows
Stable Channel / Beta Channel info: https://docs.docker.com/docker-for-windows/install/
```

- After installation, look for MobyLinuxVM in Hyper-V
- Look at the Docker UI
- Look at the Kitematic UI

Install PowerShell support
```console
Install-module posh-docker -Verbose
```

Navigate and look at Docker installation
```console
C:\ProgramData\Docker
C:\Program Files\Docker
```