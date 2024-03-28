# Base Docker Image

* [java:8-jdk-alpine](https://registry.hub.docker.com/_/java/)

# Docker Tags

* 3.1.0
* 3.1.0.1
* 3.1.1
* 3.1.2
* 3.1.3
* 3.2.0
* 3.2.1 
* 3.9.5 (stable)
Note: Gatling versions from 2.1.0 to 2.2.5 are built with Scala 2.11, versions from 2.3.0 onwards are built with Scala 2.12.

# Installation

* Install [Docker](https://www.docker.com/)

* Get automated build from public registry:

Latest version:

`docker pull phuctri1510/gatling:latest`

All versions:

`docker pull phuctri1510/gatling`

Specific version:

`docker pull phuctri1510/gatling:3.2.1`

* [Alternatively] Build an image from Dockerfile: `docker build -t="phuctri1510/gatling" github.com/phuctri1510/gatling-docker`

# Usage

Use image to run container

```
docker run -it --rm phuctri1510/gatling
```

Mount configuration and simulation files from the host machine and run gatling in interactive mode

```
docker run -it --rm -v /home/core/gatling/conf:/opt/gatling/conf \
-v /home/core/gatling/user-files:/opt/gatling/user-files \
-v /home/core/gatling/results:/opt/gatling/results \
denvazh/gatling
```

Use the `-e` switch to use JAVA_OPTS to pass parameters to gatling tests

```
docker run -e JAVA_OPTS="-Dusers=10" -it --rm denvazh/gatling
```
